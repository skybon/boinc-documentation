# BOINC GUI RPC Reference
## Definitions
It is my belief that there runs some confusion and misunderstanding when it comes to official BOINC terminology.
- **_BOINC client_** is the software daemon that runs on user's computer, downloads project jobs and manages the crunching. Despite this it is officially called _client_, probably as opposed to **_project server_** that manages the project's state and distributes workload. **However, for purposes of this documentation _BOINC client_ will be referred to as _Daemon_.**
- **_GUI_** is the software that connects to BOINC client and enables client management in a user-friendly way. **Here it will be called _Client_.**

## General format
RPC calls are made via _TCP_ connections established by a Client connecting to Daemon. The format of requests and replies is specified below.
- _Client to Daemon_: `<boinc_gui_rpc_request> content </boinc_gui_rpc_request>\x03`
- _Daemon to Client_: `<boinc_gui_rpc_reply> content </boinc_gui_rpc_reply>\x03`

## Requests
### Authentication
This is the first step that is necessary for communication if RPC password is not empty. All other requests will return `<unauthorized/>` until handshake is complete using `auth1` and `auth2`.

#### Calls
##### Auth1
- Description: starts authentication. Daemon sends back a salt that will be used in the next step.
- Client request: `<auth1/>`
- Daemon response: `<nonce>{ salt for authentication }</nonce>`

##### Auth2
- Description: take salt from Auth1, prepend it to RPC password and hash with MD5. In short, `md5(nonce+password)`.
- Client request: `<auth2><nonce_hash>{ the hash }</nonce_hash></auth>`
- Daemon response: `<authorized/>` is successful, `<unauthorized/>` if not.

### Daemon status
View and control Daemon's general status.

#### Schemas
##### Log message

```
<msg>
    <project>{ project name, string }</project>
    <pri>{ message priority, int }</pri>
    <seqno>{ message number, int }</seqno>
    <body>{ message text, string }</body>
    <time>{ time of message, Unix timestamp (int) }</time>
</msg>
```

#### Calls
##### Get message count
- Description: receive number of messages in Daemon's event log.
- Client request: `<get_message_count/>`
- Daemon response: `<seqno>{ num of messages }</seqno>`

##### Get messages
- Description: receive messages, _starting from_ num.
- Client request: `<get_messages><seqno>{ num }</seqno></get_messages>`
- Daemon response: `<msgs>{ messages, starting from num+1 until the end }</msgs>`

##### Set CPU status
- Description: sets Daemon CPU activity status.
- Client request: `<set_run_mode>{ mode }<duration>{ set status for this amount of time, sec; 0 for permanent }</duration></set_run_mode>`
- Daemon response: `<success/>` on success.

##### Set GPU status
- Description: sets Daemon GPU activity status.
- Client request: `<set_gpu_mode>{ mode }<duration>{ set status for this amount of time, sec; 0 for permanent }</duration></set_run_mode>`
- Daemon response: `<success/>` on success.

##### Set network status
- Description: sets Daemon network activity status.
- Client request: `<set_network_mode>{ mode }<duration>{ set status for this amount of time, sec; 0 for permanent }</duration></set_run_mode>`
- Daemon response: `<success/>` on success.

### Projects and account managers
Get and manage project list of the client.

#### Schemas
##### Platforms list schema

```
<platforms>
    <name>{ platform A, string }</name>
    <name>{ platform B, string }</name>
    <name>{ platform C, string }</name>
    ...
</platforms>
```

##### Project info

```
<project>
    <name>{ project name }</name>
    <summary>{ project's goal }</summary>
    <url>{ project url }</url>
    <general_area>{ project's field of study }</general_area>
    <specific_area>{ project's subfield }</specific_area>
    <description>{ project description }</description>
    <home>{ where project is hosted }</home>
    <platforms>{ list of platform names for which applications are available. See plarforms list schema above. }</platforms>
    <image>{ url of the project's logo }</image>
</project>
```

##### Project list

```
<projects>
    <project>{ project A }</project>
    <project>{ project B }</project>
    <project>{ project C }</project>
    ...
</projects>
```

##### Account manager information

```
<acct_mgr_info>
    <acct_mgr_url>{ URL of the account manager }</acct_mgr_url>
    <acct_mgr_name>{ Name of the account manager }</acct_mgr_name>
    <have_credentials/> <!-- if logged in -->
    <cookie_required/> <!-- if authentication required -->
    <cookie_failure_url></cookie_failure_url>
</acct_mgr_info>
```

#### Calls
##### Get all projects list
- Description: get all projects that are in Daemon's database. Note that this includes all projects known to Daemon, not just those you are connected to.
- Client request: `<get_all_projects_list/>`
- Daemon response: `<projects>{ array of projects, see Project list schema above }</projects>`

##### Get account manager info
- Description: get information about account manager.
- Client request: `<acct_mgr_info/>`
- Daemon response: `<acct_mgr_info>{ account manager information }</acct_mgr_info>`

##### Poll account manager status
- Description: get status on account manager attach / manipulation. See Status code reference for more info.
- Client request: `<acct_mgr_rpc_poll/>`
- Daemon response: `<acct_mgr_rpc_reply><error_num>{ status }</error_num></acct_mgr_rpc_reply>`

# BOINC status codes

Name                             | Code | Interpretation
-------------------------------- | ---- | -------------------------------------------------------------------------------------------------------
BOINC_SUCCESS                    | 0    | Nominal
EXIT_STATEFILE_WRITE             | 192  |
EXIT_SIGNAL                      | 193  | Error on writing statefile
EXIT_ABORTED_BY_CLIENT           | 194  | Killed by signal
EXIT_CHILD_FAILED                | 195  |
EXIT_DISK_LIMIT_EXCEEDED         | 196  |
EXIT_TIME_LIMIT_EXCEEDED         | 197  |
EXIT_MEM_LIMIT_EXCEEDED          | 198  |
EXIT_CLIENT_EXITING              | 199  |
EXIT_UNSTARTED_LATE              | 200  |
EXIT_MISSING_COPROC              | 201  |
EXIT_ABORTED_BY_PROJECT          | 202  |
EXIT_ABORTED_VIA_GUI             | 203  |
EXIT_UNKNOWN                     | 204  |
EXIT_OUT_OF_MEMORY               | 205  |
ERR_SELECT                       | -100 |
ERR_MALLOC                       | -101 |
ERR_READ                         | -102 |
ERR_WRITE                        | -103 |
ERR_FREAD                        | -104 |
ERR_FWRITE                       | -105 |
ERR_IO                           | -106 |
ERR_CONNECT                      | -107 |
ERR_FOPEN                        | -108 |
ERR_RENAME                       | -109 |
ERR_UNLINK                       | -110 |
ERR_OPENDIR                      | -111 |
ERR_XML_PARSE                    | -112 | Unexpected XML tag or XML format
ERR_GETHOSTBYNAME                | -113 | Couldn't resolve hostname
ERR_GIVEUP_DOWNLOAD              | -114 | too much time has elapsed without progress on file xfer / got a 404 (not found) status code from server
ERR_GIVEUP_UPLOAD                | -115 |
ERR_NULL                         | -116 | Unexpected null pointer
ERR_NEG                          | -117 | Unexpected negative value
ERR_BUFFER_OVERFLOW              | -118 | Caught buffer overflow
ERR_MD5_FAILED                   | -119 | MD5 checksum failed for a file
ERR_RSA_FAILED                   | -120 | RSA key check failed for a file
ERR_OPEN                         | -121 |
ERR_DUP2                         | -122 |
ERR_NO_SIGNATURE                 | -123 |
ERR_THREAD                       | -124 | Error creating a thread
ERR_SIGNAL_CATCH                 | -125 |
ERR_BAD_FORMAT                   | -126 |
ERR_UPLOAD_TRANSIENT             | -127 |
ERR_UPLOAD_PERMANENT             | -128 |
ERR_IDLE_PERIOD                  | -129 | can't start work because of user prefs
ERR_ALREADY_ATTACHED             | -130 |
ERR_FILE_TOO_BIG                 | -131 | an output file was bigger than max_nbytes
ERR_GETRUSAGE                    | -132 | getrusage failed
ERR_BENCHMARK_FAILED             | -133 |
ERR_BAD_HEX_FORMAT               | -134 | hex-format key data is bad
ERR_GETADDRINFO                  | -135 |
ERR_DB_NOT_FOUND                 | -136 | no rows found in lookup() or enumerate()
ERR_DB_NOT_UNIQUE                | -137 | not unique in lookup()
ERR_DB_CANT_CONNECT              | -138 |
ERR_GETS                         | -139 | gets() or fgets()
ERR_SCANF                        | -140 | scanf() or fscanf()
ERR_READDIR                      | -143 |
ERR_SHMGET                       | -144 |
ERR_SHMCTL                       | -145 |
ERR_SHMAT                        | -146 |
ERR_FORK                         | -147 |
ERR_EXEC                         | -148 |
ERR_NOT_EXITED                   | -149 | a process didn't exit that was supposed to
ERR_NOT_IMPLEMENTED              | -150 | a system call not implemented on this platform
ERR_GETHOSTNAME                  | -151 |
ERR_NETOPEN                      | -152 |
ERR_SOCKET                       | -153 |
ERR_FCNTL                        | -154 |
ERR_AUTHENTICATOR                | -155 | scheduler request host ID doesn't match authenticator
ERR_SCHED_SHMEM                  | -156 | sched shmem has bad contents
ERR_ASYNCSELECT                  | -157 |
ERR_BAD_RESULT_STATE             | -158 |
ERR_DB_CANT_INIT                 | -159 |
ERR_NOT_UNIQUE                   | -160 | state files had redundant entries
ERR_NOT_FOUND                    | -161 | catch-all lookup error
ERR_NO_EXIT_STATUS               | -162 | exit_status not found in scheduler request
ERR_FILE_MISSING                 | -163 |
ERR_KILL                         | -164 |
ERR_SEMGET                       | -165 |
ERR_SEMCTL                       | -166 |
ERR_SEMOP                        | -167 |
ERR_FTOK                         | -168 |
ERR_SOCKS_UNKNOWN_FAILURE        | -169 |
ERR_SOCKS_REQUEST_FAILED         | -170 |
ERR_SOCKS_BAD_USER_PASS          | -171 |
ERR_SOCKS_UNKNOWN_SERVER_VERSION | -172 |
ERR_SOCKS_UNSUPPORTED            | -173 |
ERR_SOCKS_CANT_REACH_HOST        | -174 |
ERR_SOCKS_CONN_REFUSED           | -175 |
ERR_TIMER_INIT                   | -176 |
ERR_INVALID_PARAM                | -178 |
ERR_SIGNAL_OP                    | -179 |
ERR_BIND                         | -180 |
ERR_LISTEN                       | -181 |
ERR_TIMEOUT                      | -182 |
ERR_PROJECT_DOWN                 | -183 |
ERR_HTTP_TRANSIENT               | -184 | HTTP errors other than 404 and 416
ERR_RESULT_START                 | -185 |
ERR_RESULT_DOWNLOAD              | -186 |
ERR_RESULT_UPLOAD                | -187 |
ERR_BAD_USER_NAME                | -188 |
ERR_INVALID_URL                  | -189 |
ERR_MAJOR_VERSION                | -190 |
ERR_NO_OPTION                    | -191 |
ERR_MKDIR                        | -192 |
ERR_INVALID_EVENT                | -193 |
ERR_ALREADY_RUNNING              | -194 |
ERR_NO_APP_VERSION               | -195 |
ERR_WU_USER_RULE                 | -196 |
ERR_ABORTED_VIA_GUI              | -197 |
ERR_INSUFFICIENT_RESOURCE        | -198 |
ERR_RETRY                        | -199 |
ERR_WRONG_SIZE                   | -200 |
ERR_USER_PERMISSION              | -201 | e.g. user didn't allow network connection
ERR_SHMEM_NAME                   | -202 |
ERR_NO_NETWORK_CONNECTION        | -203 |
ERR_IN_PROGRESS                  | -204 |
ERR_BAD_EMAIL_ADDR               | -205 |
ERR_BAD_PASSWD                   | -206 |
ERR_NONUNIQUE_EMAIL              | -207 |
ERR_ACCT_CREATION_DISABLED       | -208 |
ERR_ATTACH_FAIL_INIT             | -209 |
ERR_ATTACH_FAIL_DOWNLOAD         | -210 |
ERR_ATTACH_FAIL_PARSE            | -211 |
ERR_ATTACH_FAIL_BAD_KEY          | -212 |
ERR_ATTACH_FAIL_FILE_WRITE       | -213 |
ERR_ATTACH_FAIL_SERVER_ERROR     | -214 |
ERR_SIGNING_KEY                  | -215 |
ERR_FFLUSH                       | -216 |
ERR_FSYNC                        | -217 |
ERR_TRUNCATE                     | -218 |
ERR_WRONG_URL                    | -219 |
ERR_DUP_NAME                     | -220 |
ERR_GETGRNAM                     | -222 |
ERR_CHOWN                        | -223 |
ERR_HTTP_PERMANENT               | -224 | represents HTTP 404 or 416 error
ERR_BAD_FILENAME                 | -225 |
ERR_TOO_MANY_EXITS               | -226 |
ERR_RMDIR                        | -227 |
ERR_SYMLINK                      | -229 |
ERR_DB_CONN_LOST                 | -230 |
ERR_CRYPTO                       | -231 |
ERR_ABORTED_ON_EXIT              | -232 |
ERR_PROC_PARSE                   | -235 |
ERR_STATFS                       | -236 |
ERR_PIPE                         | -237 |
ERR_NEED_HTTPS                   | -238 |
ERR_CHMOD                        | -239 |
ERR_STAT                         | -240 |

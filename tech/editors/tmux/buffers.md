# Buffers
* **note** I can't type pipe character in tables as it is a special spacing character so type PIPE in its place
* so `:%bdPIPEe#` would be `:bd|e#`  

| key binding         | action                                                 | notes                     |
|---------------------|--------------------------------------------------------|---------------------------|
| `bufdo bd`          | blow up all buffers but this one                       |                           |
| `:%bdPIPEe#`        | delete all buffers                                     | PIPE is the vertical pipe |
| `:%bdPIPEe#PIPEbd#` | delete all buffers and No Name buffer too              | PIPE is the vertical pipe  |
| `%bd`               | delete buffer                                          | na                        |
| `e#`                | open the last buffer for editing                       | na                        |
| `PIPE`              | The pipe inbetween just does one command after another | PIPE is the vertical pipe |

# ansible-role-fish

This role sets install the fish shell and can configure aliases (functions).

## Example

### Basic Usage

```
- name: play with fish
  vars:
    fish_variables:
      - name: SSH_AUTH_SOCK
        value: ~/.cache/ssh-agent.socket
    fish_functions:
      - name: httpath
        description: "Show HTTP(s) Headers with curl and a nice output"
        command: "curl -L -s -v -o /dev/null $argv"
  roles:
    - benibr.fish
```


### Usage for macOS with homebrew
```
- name: play with fish
  vars:
    fish_exe_path: "/opt/homebrew/Cellar/fish/3.6.1/bin/fish"
    fish_tmux_path: "/opt/homebrew/bin/tmux"
    fish_local_tmux: yes 
    fish_variables:
      - name: PATH
        value: /opt/homebrew/opt/gnu-sed/libexec/gnubin:/opt/homebrew/bin/:$PATH
      - name: VAULT_ADDR
        value: https://vaultp.it.ku.dk
      - name: NETBOX_API
        value: https://ipam.it.ku.dk
      - name: NETBOX_TOKEN
        value: (cat ~/.config/netbox_token)
      - name: OBJC_DISABLE_INITIALIZE_FORK_SAFETY
        value: YES 
  roles:
    - benibr.fish
```

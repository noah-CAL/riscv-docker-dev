# RISCV-V Docker Development Container

This is a docker image which has the RISC-V toolchain + devtools installed alongside a two-command Makefile for easy development of RISC-V tools.

## Getting Started

The first prerequisite is to have Docker / Docker Desktop installed. 

There are two commands to get up and running:

```make build_docker```

...will build the Docker image. Note that this needs **~8GB storage space** and may take **several hours to complete** as it downloads and sets up the RISC-V toolchain. It is advised to run in a separate background process with `make build_docker &` and monitor the logs with Docker Desktop or a process viewer like `htop`.

Once complete:
```make shell```

Will mount the current directory to the `/src` directory and will sync all files with the Docker container. From here, a login message will display the avaiable `RISC-V` tooling commands (`gcc`, `cpp`, `objdump`, `objcopy`, etc.) available on the PATH and can be run with `riscv64-unknown-elf-gcc ...`.

Changes will sync between the Docker image and your current working directory. A terminal multiplexor ([tmux](https://github.com/tmux/tmux/wiki)) may be helpful for managing multiple shell sessions.


## TODO list
+ Add Spike simulator
+ Add options to configure for RV32 architecture + simulations

Feel free to help out!

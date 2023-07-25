# action-build-stm32cubeide-demo
Demo for action-build-stm32cubeide

## Flow
- Generate artifact name from SHORT_SHA and REF_NAME.  
  Artifact will be named demo_project._REF_NAME_._SHORT_SHA_.zip
  e.g. demo_project.main.dc8af4b8.zip for main builds or demo_project.v1.0.0.f00dface.zip for the tag v1.0.0
  
- Prepare [act](https://github.com/nektos/act) run if run locally

- Checkout source

- Prepare git in container.  
  This is required for generating the gitid.h from the STM32 build environment else it complains with kind of safe_directory error.

- Import and build the project using the [action-build-stm32cubeide](https://github.com/philippdiethelm/action-build-stm32cubeide) action

- Create and upload artifact.  
  demo_project._REF_NAME_._SHORT_SHA_.zip:
  - gitid.h
  - Debug/demo_project.elf
  - Debug/demo_project.list
  - Release/demo_project.elf
  - Release/demo_project.list
  

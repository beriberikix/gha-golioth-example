# GitHub Actions example for Zephyr applications

This is an example showing how to use GitHub Actions to automate certain tasks when developing an application with Zephyr RTOS.

## Basics

The example assumes that the main `west.yml` file will be in the top directory and all app code will be in the `app` folder.

[Variables](https://docs.github.com/en/actions/learn-github-actions/variables#using-the-vars-context-to-access-configuration-variable-values) are used to simplify configuration. Add repo-level variables under Settings > Secrets and variables > Actions > Variables.

## Build action

The build action in `build.yml` that builds the application on pushes to main, semvar tags or PRs to main. It builds for a single target and uploads the results as a GitHub Action Artifact that can be downloaded later.

Create the following variables:
- ZEPHYR_VERSION
- ZEPHYR_SDK_VERSION
- TOOLCHAIN
- BOARD

Example values would be:
- ZEPHYR_VERSION: `v3.2.0`
- ZEPHYR_SDK_VERSION: `0.15.2`
- TOOLCHAIN: `arm-zephyr-eabi`
- BOARD: `reel_board`
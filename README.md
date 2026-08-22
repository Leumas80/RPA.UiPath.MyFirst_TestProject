<p align="center">
  <img src=".package/IniciaME.png" alt="IniciaME Logo" width="80">
</p>

# RPA.UiPath.MyFirst_TestProject

Automated background testing project built with **UiPath Studio (v25.0)** and **UiPath Test Framework**, tailored for seamless integration and remote execution via **IniciaME TM Executor**.

## Key Features
* **Background Execution**: Configured with `requiresUserInteraction: false` and `targetFramework: Portable` to execute headless workflows without locking user desktop sessions or requiring UI interaction.
* **Minimal Footprint**: Operates exclusively on core dependencies (`UiPath.System.Activities` and `UiPath.Testing.Activities`) ensuring minimal resource overhead and rapid initialization.
* **Dynamic Assertions & Simulation**: Built upon `.templates\TestFramework.xaml` with a 30% synthetic error-margin logic for end-to-end testing of execution status reporting (`Passed` / `Failed`).

## Validation Logic Flow
The primary workflow (`MFP_My First TestCase.xaml`) executes three sequential assertions:
1. **Initial Greeting**: Asserts initial execution logging under the signature `Inicia.ME`.
2. **Context Explanation**: Evaluates a dynamically generated integer (`intRandom` between 1 and 100) and logs the test run parameters.
3. **Margin Validation (`IfElseIf`)**:
   * **`intRandom > 30` (70% probability)**: Evaluates to `True` $\rightarrow$ Logs *"Test passed"*.
   * **`intRandom <= 30` (30% probability)**: Evaluates to `False` $\rightarrow$ Logs *"Test fail"*.

## Technical Specifications
* **Project Type**: Test Automation (`outputType: Tests`)
* **Expression Language**: VisualBasic (.NET)
* **Framework Target**: Portable / Cross-Platform
* **Runtime**: Unattended / Background (`isAttended: false`)

## Setup & Publishing
1. Open the project in **UiPath Studio** (2024.10+ / 2025+).
2. Validate `MFP_My First TestCase.xaml`.
3. Publish the package to Orchestrator / Test Manager feeds to enable remote execution and bi-directional labeling via **IniciaME TM Executor**.

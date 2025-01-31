```markdown
# Maestro Project for UI Automation for the JetNews App

This project leverages the [Maestro framework](https://maestro.mobile.dev) to automate UI testing for the Jetnews application, ensuring a seamless user experience by verifying key functionality and interactions.

## Test Cases

The following test cases are automated using the Maestro framework:

- **Opening the Application**: Verifies that the user can launch the Jetnews app.
- **Menu Navigation**: Ensures the menu opens correctly.
- **Navigating to “Interests”**: Tests that the user can navigate to the "Interests" section.
- **Selecting a “Topic”**: Confirms that the user can select a topic within the Interests section.
- **Content Loading**: Verifies that the correct posts are displayed after selecting a topic.

## Project Structure

## Pages

The **Pages** directory contains YAML files that define the individual steps required to interact with various screens in the Jetnews app.

- **MainPage.yaml**: Defines the steps to verify functionality on the main page of the Jetnews application, such as opening the app and validating the tests and closing the app after execution.
### Tests

The **Tests** directory holds YAML files for the test flows, linking different page steps together to perform end-to-end UI tests.

- **hometest.yaml**: This file combines steps from multiple page definitions (e.g., setup.yaml) to execute an end-to-end test that ensures core functionality like launching the app, expanding the sidebar, and validating its content .
  
- **intereststest.yaml**: Automates the process of navigating to the Interests page, interacting with various tests and tabs, and performing assertions on the displayed content. It also includes a scroll to the bottom of the page and verifies the presence of a specific text element.

## Getting Started

To begin running automated tests with Maestro, follow the setup and configuration steps below.

## Prerequisites

Ensure you have the following installed on your machine:

- [Maestro Framework](https://maestro.mobile.dev/getting-started/installing-maestro) (for UI test automation)
- The **Jetnews** application installed on a physical device or emulator

## Environment Setup

1. **Clone the repository**:

   ```sh
   git clone https://github.com/kamowilson/maestro_uiautomation_sample.git
   cd maestro-project
   ```

2. **Install Maestro** (if you haven't already):

   Follow the installation guide for [Maestro](https://maestro.mobile.dev/getting-started/installing-maestro) depending on your OS.

3. **Install Jetnews App**:

   - Clone the repository https://github.com/renatibrahimov/test-assignment and run the project

4. **Connect Device or Emulator**:

   Ensure a physical device or emulator is running. Maestro supports both Android and iOS devices. Do not run both emulators together, instead one at a time.

## Running the Tests

Once the setup is complete, you can run the tests with the following command:

1. **Execute Home Test**:

   ```sh
   maestro test tests/hometest.yaml
   ```

   This command runs the `hometest.yaml` test, verifying that the app's main page works as expected.

2. **Execute Interests Test**:

   ```sh
   maestro test tests/intereststest.yaml
   ```

   This will trigger the `intereststest.yaml`, testing navigation and content validation in the "Interests" section.

3. **Run the entire test suite in one**:

   ```sh
   maestro test MainPage.yaml
   ```

   This will trigger the `MainPage.yaml`, file and run all test subflows in the test suite

## Extras
Start recording and Stop recording commands create an mP4 file after execution of test that can be played to follow the steps of the test execution

## Customizing the Tests

Feel free to modify the YAML test definitions as per your application's specific requirements. You can add more pages, test cases, or assertions.

## Configuring Maestro

You can configure Maestro using the `maestro.yaml` configuration file to adjust device settings, app paths, and other parameters. A sample configuration might look like:

```yaml
device:
  platform: android
  device_id: emulator-5554
  udid: emulator-5554

app:
  path: ./path/to/Jetnews.apk
```

## Contributing

We welcome contributions to improve the project! Here’s how you can contribute:

1. Fork the repository.
2. Create a new branch for your changes.
3. Write tests and documentation.
4. Create a pull request to merge your changes.

## Troubleshooting

- **Test failures**: If tests fail, check for issues with your device/emulator setup, application installation, or page element selectors.
- **Device not found**: Make sure your physical device/emulator is properly connected and running. You can verify with `adb devices` (Android) or `xcrun simctl list` (iOS).
  
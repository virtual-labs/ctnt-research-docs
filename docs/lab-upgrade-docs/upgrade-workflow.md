# General Workflow for Upgrading the Experiment Code in Lab Repositories

This document provides a detailed overview of the general workflow for upgrading the experiment code in Virtual Labs repositories to ensure the smooth and efficient operation of the labs.

## Table of Contents

- [General Workflow for Upgrading the Experiment Code in Lab Repositories](#general-workflow-for-upgrading-the-experiment-code-in-lab-repositories)
  - [Table of Contents](#table-of-contents)
  - [Audience](#audience)
  - [What is the Need for Code Upgrade?](#what-is-the-need-for-code-upgrade)
  - [What Needs to be Updated?](#what-needs-to-be-updated)
  - [Tools Used and Methodology](#tools-used-and-methodology)
  - [General Workflow](#general-workflow)
  - [Additional Information](#additional-information)

## Audience

This documentation is intended for developers responsible for upgrading the remaining labs that use outdated versions or libraries.

## What is the Need for Code Upgrade?

It is essential to upgrade the code in Virtual Labs repositories to:

- Maintain compatibility with current operating systems and software versions.
- Ensure the availability of the latest features and bug fixes.
- Improve the performance and security of the labs.
- Adhere to industry best practices and standards.

## What Needs to be Updated?

The following aspects of the experiment code may require upgrading:

- PHP versions: Experiment simulations and assignments written in outdated PHP versions (4 or 5) should be upgraded to PHP 8.
- External libraries: Labs that depend on specific external libraries (e.g., OpenCV, Octave) may require code refactoring to ensure compatibility with the latest versions.

## Tools Used and Methodology

Rector and ChatGPT are the primary tools used for the code upgrade process:

- **Rector:** Automates the upgrading of PHP code from older versions to newer ones.
- **ChatGPT:** Assists with other upgrades, such as rewriting code in the latest released version for cases where automated upgrade is not possible.

## General Workflow

1. **Assessment of Current Code:**
   - Determine the current version of PHP and any external libraries used in the experiment code.
   - Identify the specific areas of code that require updating.

2. **Upgrade Planning:**
   - Create a plan for the upgrade process, including the target PHP version and required library updates.
   - Establish a schedule for the implementation and testing of the upgraded code.

3. **Automated Upgrade Using Rector:**
   - Install Rector and configure it for the target PHP version.
   - Run Rector to automatically upgrade the codebase.

4. **Manual Upgrades and Refactoring:**
   - For any code that cannot be upgraded automatically, manually refactor the code to the latest released version.
   - Use ChatGPT to assist with the rewriting process as needed.

5. **Testing and Debugging:**
   - Test the upgraded codebase thoroughly to ensure it functions as expected.
   - Debug any issues that arise during testing and make necessary adjustments to the code.

6. **Deployment and Monitoring:**
   - Deploy the upgraded code to the lab repositories.
   - Monitor the performance and functionality of the upgraded labs to ensure they are operating smoothly.

## Additional Information

- The upgrade process may vary depending on the specific lab and the extent of the changes required.
- It is recommended to create backups of the codebase before performing any upgrades.
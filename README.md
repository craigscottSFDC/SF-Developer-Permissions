# Developer Read-Only Permissions

This repository contains Salesforce metadata files that define access for developers in higher environments (e.g., QA, UAT). The purpose of these permissions is to allow developers to confirm their work and inspect configurations without having the ability to modify metadata or configuration in these environments.

## Files Included

The following core files are included:

* `Developer User.profile-meta.xml`: Defines the profile settings for the "Developer User."
* `Developer_Test_Access.permissionsetgroup-meta.xml`: A permission set group providing access for testing purposes.
* `Developer_Test_Access_Muted.mutingpermissionset-meta.xml`: A muting permission set designed to restrict specific permissions within the `Developer_Test_Access` group, ensuring metadata and configuration cannot be modified.
* `Developer_Testing_Access.permissionset-meta.xml`: A permission set specifically for developers needing access during testing phases.

## `package.xml`

A `package.xml` file is included in this repository which references and facilitates the deployment of these permission files. This `package.xml` ensures that all necessary components for these read-only permissions can be deployed together.

## Purpose

The primary goal of these permissions is to:

* **Enable Verification:** Allow developers to verify their deployed changes in non-production environments.
* **Prevent Accidental Modification:** Ensure that developers cannot inadvertently alter configurations or metadata in sensitive higher environments.
* **Streamline QA Process:** Provide a controlled environment for developers to assist in troubleshooting or validating fixes during QA cycles.

## Usage

These files are intended to be deployed to Salesforce environments where developers require access. They can be deployed using standard Salesforce CLI commands or other metadata deployment tools.

**Important Note on Customization:**

The permission set, permission set group, and profile files (`.permissionset-meta.xml`, `.permissionsetgroup-meta.xml`, and `.profile-meta.xml`) provided in this repository are generic examples. **You will need to review and update these files to reference anything specific to your project's objects, fields, classes, Visualforce pages, Apex classes, custom settings, or any other metadata components unique to your environment(s) where access is desired.** Failure to do so may result in developers not having visibility into the necessary components for their verification tasks.

**Note:** Always review and understand the permissions defined in these files before deploying them to any environment.

---

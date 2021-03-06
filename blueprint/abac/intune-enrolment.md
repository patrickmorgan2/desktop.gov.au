---
layout: page
title: Intune enrolment
menu: abac
---

## Automatic enrolment

`Intune > Devices > Enroll devices > Automatic Enrollment`

Item | Configuration
--- | ---
MDM user scope | Some - grp-Agency-IntuneEnrolment
Groups | 1 Group selected
MDM terms of use URL | `https://portal.manage.microsoft.com/TermsofUse.aspx`
MDM discovery URL | `https://enrolment.manage.microsoft.com/enrolmentserver/discovery.svc`
MDM Compliance URL | `https://portal.manage.microsoft.com/?portalAction=Compliance`
MAM user scope | Some
Groups | grp-Agency-IntuneEnrolment
MAM terms of use URL | Not configured
MAM discovery URL | `https://wip.mam.manage.microsoft.com/Enroll`
MAM compliance URL | Not configured`

## Enrolment status page

`Intune > Devices > Enroll devices > Enrollment Status Page`

* Name: `All users and all devices`
* Description: `This is the default enrolment status screen configuration applied with the lowest priority to all users and all devices regardless of group membership`
* Settings
  * Show app and profile configuration progress: `Yes`
  * Show an error when installation takes longer than specified number of minutes: `60`
  * Show custom message when time limit error occurs: `Yes`
  * Error message: `Installation exceeded the time limit set by your organisation. Please try again or contact IT support for help.`
  * Allow users to collect logs about installation errors: `Yes`
  * Only show page to devices provisioned by out-of-box experience (OOBE): `No`
  * Block device use until all apps and profiles are installed: `Yes`
  * Allow users to reset device if installation error occurs: `No`
  * Allow users to use device if installation error occurs: `Yes`
  * Block device use until these required apps are installed if they are assigned to the user/device: `Defender ATP Registry Recommendations`, `Office 365 Monthly Targeted`
* Assignments
  * Included groups: `All devices`

## Deployment profiles

`Intune > Devices > Enroll devices > Deployment Profiles`

* Name: `IntuneEnrollerDevices`
* Description: `Devices enrolled in Intune via autopilot`
* Convert all targeted devices to Autopilot: `No`
* Device type: `Windows PC`
* Out-of-box experience (OOBE)
  * Deployment mode: `User-Driven`
  * Join to Azure AD as: `Azure AD Joined`
  * Language (Region): `English (Australia)`
  * Automatically configure keyboard: `Yes`
  * Microsoft Software License Terms: `Hide`
  * Privacy settings: `Hide`
  * Hide change account options: `Hide`
  * User account type: `Standard`
  * Allow White Glove OOBE: `Yes`
  * Apply device name template: `Yes`
  * Enter a name: `<Agency 3 characters>-%SERIAL%`
* Scope tags: `Default`
* Assignments
  * Included groups: `grp-Security-Baselines`
  * Excluded groups: -

## Windows Hello for Business

`Intune > Devices > Enroll devices > Windows Hello for Business`

Item | Configuration
--- | ---
Assigned to | All users
Name | All users and all devices
Description | This is the default Windows Hello for Business configuration applied with the lowest priority to all users regardless of group membership.
Configure Windows Hello for Business | Disabled
Use a Trusted Platform Module (TPM) | Preferred
Minimum PIN Length | 4
Maximum PIN Length | 127
Lowercase letters in PIN | Allowed
Uppercase letters in PIN | Allowed
Special characters in PIN | Allowed
PIN expiration (days) | Never
Remember PIN history | No
Allow biometric authentication | No
Use enhanced anti-spoofing, when available | Yes
Allow phone sign-in | No
Use security keys for sign-in | Not configured

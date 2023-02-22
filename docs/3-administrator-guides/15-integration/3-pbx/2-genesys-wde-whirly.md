---
title: Genesys WDE by Whirly
description: PBX integration via Genesys Workspace Desktop Edition
keywords:
  - Integration
  - PBX
  - Genesys
  - YetiForce
tags:
  - PBX
  - Genesys
preview: genesys-wde-whirly.jpg
---

PBX integration via Genesys Workspace Desktop Edition.

![genesys-wde-whirly.jpg](genesys-wde-whirly.jpg)

## Configuration

In order to enable the integration, follow the steps below:

### Add configuration to PBX

Add an entry to the PBX with the following type: `Genesys WDE by Whirly`

Provide the following information in the window:

- HTTP listening port - the number of the local port used by the WDE application for listening
- Phone - required for outgoing calls; the PBX supports multiple phone numbers and you must specify which one is used when a phone number is clicked.
- Email - required for sending emails, the PBX supports emails and you must specify which address is used when you click on an email address.

![genesys-wde-whirly-1.jpg](genesys-wde-whirly-1.jpg)

### Activation for users

The next step is to activate the integration for users; by default the system uses basic protocol support for telephone and e-mail address.

Go to the user whose integration you want to enable and find the fields:

- Genesys Agent ID (block `Basic information`) - enter the user's login in Genesys WDE

![genesys-wde-whirly-2.jpg](genesys-wde-whirly-2.jpg)

- Mail composer (block `Integration with mail`) - select `Genesys WDE by Whirly`
- User PBX (block `Phone branch exchange`) - select the name you previously entered in [Add configuration to PBX](#add-configuration-to-pbx)

![genesys-wde-whirly-3.jpg](genesys-wde-whirly-3.jpg)

### Add configuration to API

Each interaction sends a request to the API with full data and in response the YetiForce system returns a URL to be enabled for the user in Genesys WDE.

In oder to do that add PBX type configuration in [`Software configuration → Integration → Web service - Applications`](/administrator-guides/integration/webservice-apps/).

![genesys-wde-whirly-4.jpg](genesys-wde-whirly-4.jpg)

Then copy the key and paste it in Genesys Administrator configuration.

![genesys-wde-whirly-5.jpg](genesys-wde-whirly-5.jpg)

### Add configuration to Genesys Administrator

Enter the following parameters in the Genesys Administrator panel:

- Endpoint `__YETIFORCE_PATH__`/webservice/PBX/GenesysWdeWhirly/
- Token/key generated in `Web service - Applications`

![genesys-wde-whirly-6.jpg](genesys-wde-whirly-6.jpg)

## External links

- https://www.genesys.com/collateral/genesys-workspace

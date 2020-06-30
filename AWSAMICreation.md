![Minnesota IT Services
logo](./media/image1.png){width="4.166668853893263in" height="1.75in"}

AWS -- Creating New AMI Images

Version 1.0

3/26/2018

Table of Contents
=================

[Table of Contents 2](#table-of-contents)

[1. Executive Summary 3](#executive-summary)

[2. Create New Linux AMIs 3](#create-new-amis)

[3. Document Revision History 6](#document-revision-history)

1. Executive Summary
====================

AMI (Amazon Machine Images) are used to deploy instances in Amazon EC2.

Every 3^rd^ Sunday of the month @ 03:00, there is a Cloudwatch event
that launches the SSM document to create the Windows 2012r2, Windows
2016 and Red Hat 7 MNIT Enterprise AMIs. These AMIs are shared out to
all the agencies' VPCs.

This document provides the steps necessary to manually create these
AMIs.

2. Create New AMIs
==================

Sign into the MN-MNIT-MGMT Account .

At the AWS services dashboard, under Compute, select EC2.

![](./media/image2.png){width="2.8773589238845143in"
height="2.7603926071741034in"}

In the left panel, uder "SYSTEM MANAGER SERVICES", select Automations.

![](./media/image3.png){width="1.0074201662292213in"
height="1.5283016185476817in"}

Click on the "Run automation" button.

In the Document name, in the "Owned by Me or Amazon" dropdown, select
"Owned by Me". Scroll down the list and select the document starting
with ent-ssm-docCreateAllAmi-xxxxxxxxxx , where xxxxxxxxxx is a random
list of characters.

![](./media/image4.png){width="6.5in" height="2.0972222222222223in"}

Click on the "Run automation" button.

Record the Execution ID that is displayed:

![](./media/image5.png){width="3.997916666666667in"
height="1.0849048556430447in"}

This Automation document status is shown in the Automations task list
(SYSTEMS MANAGER SERVICES -\> Automations):

![](./media/image6.png){width="6.5in" height="1.011111111111111in"}

You can click on the Automation task to the status/detail of the task.
Clicking on the Steps tab will provide the status of each step in the
Automation document.

![](./media/image7.png){width="6.5in" height="2.888888888888889in"}

Once the Automation task is complete, the new AMI should appear in the
AMI list (EC2 -\> IMAGES -\> AMI):

![](./media/image8.png){width="5.528301618547681in"
height="4.028100393700788in"}

Clicking on the AMI name and the Permissions tab will show which AWS
Account has access to this AMI:

![](./media/image9.png){width="6.5in" height="4.808333333333334in"}

3. Document Revision History
============================

  **Date**    **Description**   **Version**   **Author**
  ----------- ----------------- ------------- ------------
  3/26/2018   Initial Release   1.0           Cha Vang

Things to Add

---
title: Use Azure IoT Central audit logs | Microsoft Docs
description: Learn how to use audit logs in IoT Central to track changes made in an IoT Central application
author: dominicbetts
ms.author: dobett
ms.date: 07/25/2022
ms.topic: how-to
ms.service: iot-central
services: iot-central

# Administrator
---

# Use audit logs to track activity in your IoT Central application

This article describes how to use audit logs to track who made what changes at what time in your IoT Central applications. You can:

- Sort the audit log.
- Filter the audit log.
- Customize the audit log.
- Manage access to the audit log.

The audit log records information about who made a change, information about the modified entity, the action that made change, and when the change was made. The log tracks changes made through the UI, programatically with the REST API, and through the CLI.

The log records changes to the following IoT Central entities:

- [Users](howto-manage-users-roles.md#add-users)
- [Roles](howto-manage-users-roles.md#manage-roles)
- [API tokens](howto-authorize-rest-api.md#token-types)
- [Application template export](howto-create-iot-central-application.md#create-and-use-a-custom-application-template)
- [File upload configuration](howto-configure-file-uploads.md#configure-device-file-uploads)
- [Application customization](howto-customize-ui.md)
- [Device enrollment groups](concepts-device-authentication.md)
- [Device templates](howto-set-up-template.md)
- [Device lifecycle events](howto-export-to-blob-storage.md#device-lifecycle-changes-format)

The log records changes made by the following types of user:

- IoT Central user - the log shows the user's email.
- API token - the log shows the token name.
- Azure Active Directory user - the log shows the user email or ID.
- Service principal - the log shows the service principal name.

The log stores data for 30 days, after which it's no longer available.

The following screenshot shows the audit log view with the location of the sorting and filtering controls highlighted:

:::image type="content" source="media/howto-use-audit-logs/audit-log.png" alt-text="Screenshot that shows the audit log. The location of the sort and filter controls is highlighted." lightbox="media/howto-use-audit-logs/audit-log.png":::

## Customize the log

Select **Column options** to customize the audit log view. You can add and remove columns, reorder the columns, and change the column widths:

:::image type="content" source="media/howto-use-audit-logs/audit-logs-column-options.png" alt-text="Screenshot that shows the audit log column options." lightbox="media/howto-use-audit-logs/audit-logs-column-options.png":::

## Sort the log

You can sort the log into ascending or descending timestamp order. To sort, select **Timestamp**:

:::image type="content" source="media/howto-use-audit-logs/audit-logs-sorting.png" alt-text="Screenshot that shows how to sort the log into descending timestamp order." lightbox="media/howto-use-audit-logs/audit-logs-sorting.png":::

## Filter the log

To focus on a specific time, filter the log by time range. Select **Edit time range** and specify the range you're interested in:

:::image type="content" source="media/howto-use-audit-logs/audit-logs-time.png" alt-text="Screenshot that shows how filter the log to show the last hour of entries." lightbox="media/howto-use-audit-logs/audit-logs-time.png":::

To focus on specific entries, filter by entity type or action. Select **Filter** and use the multi-select drop-downs to specify your filter conditions:

:::image type="content" source="media/howto-use-audit-logs/audit-logs-filter.png" alt-text="Screenshot that shows how filter the log to show only updates to user entities." lightbox="media/howto-use-audit-logs/audit-logs-filter.png":::

## Manage access

The built-in **App Administrator** role has access to the audit logs by default. The administrator can grant access to other roles. An administrator can assign either **Full control** or **View** audit log permissions to other roles. To learn more, see [Manage users and roles in your IoT Central application](howto-manage-users-roles.md).

> [!IMPORTANT]
> Any user granted permission to view the audit log can see all log entries even if they don't have permission to view or modify the entities listed in the log. Therefore, any user who can view the log can view the identity of and changes made to any modified entity.

## Next steps

Now that you've learned how to manage users and roles in your IoT Central application, the suggested next step is to learn how to [Manage IoT Central organizations](howto-create-organizations.md).

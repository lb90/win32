---
title: DuplicateSiblingIDs
description: DuplicateSiblingIDs
ms.assetid: 942385A4-BD14-4046-9ABC-110B32D96BB6
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DuplicateSiblingIDs

## Text

Duplicate Automation ID \\"{0}\\" will cause ambiguity between elements.

## Type

Error

## Description

An element has the same Automation ID as another element.

This issue can cause automation problems that prevent test code from referencing the correct element.

## Possible causes

-   Sibling elements have the same Automation ID.
-   Incorrect implementation of the UIA AutomationId property.

## Related topics

<dl> <dt>

[**UIA\_AutomationIdPropertyId**](uiauto-automation-element-propids.md#uia-automationidpropertyid)
</dt> <dt>

[**IUIAutomationElement.CurrentAutomationId**](/windows/win32/UIAutomationClient/nf-uiautomationclient-iuiautomationelement-get_currentautomationid?branch=master)
</dt> </dl>

 

 




---
title: "Sample Excel Extension: ActionFilter Class"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
ms.author: gewarren
manager: douge
ms.workload: 
  - "multiple"
author: gewarren
---
# Sample Excel Extension: ActionFilter Class

This internal class extends the <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> class and represents a filter for test actions on a [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] element.

## Simple Properties

These read-only properties specify how the test action filter should be executed by the coded UI testing framework. For example, the <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> property provides the name of the action filter. Other properties get the <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> of the action filter, the <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, the <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> name for the test actions that are filtered by this test action filter. Others indicate whether to <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> and also whether the test action is <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.

## ProcessRule Method

This method is called by the coded UI testing framework, and executes the filter against the provided <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. This particular override removes a mouse choose action on a cell when the next action in the stack sends keystrokes to the cell. It then returns `false`.

## Private Methods

The `IsLeftClick` method determines whether the provided action represents a left-click of the mouse. The `AreActionsOnSameExcelCell` method determines whether two provided actions are executed on the same cell in Excel.

## See also

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>
- [Extending Coded UI Tests and Action Recordings to Support Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)

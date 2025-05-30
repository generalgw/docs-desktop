---
title: Create an Unbound Windows Forms DataGridView Control
description: Populate an unbound Windows Forms DataGridView Control programmatically and display a small amount of data in a table format without binding it to a data source.
ms.date: "01/12/2022"
ms.service: dotnet-framework
ms.custom: devdivchpfy22
dev_langs:
  - "csharp"
  - "vb"
helpviewer_keywords:
  - "DataGridView control [Windows Forms], unbound data"
  - "DataGridView control [Windows Forms], displaying data without binding to a data source"
  - "data [Windows Forms], unbound"
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
---
# How to: Create an Unbound Windows Forms DataGridView Control

The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source. This is useful when you have a small amount of data that you want to display in a table format.

For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).

## Example

[!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
[!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]

## Compiling the Code

This example requires:

- References to the System, System.Drawing, and System.Windows.Forms assemblies.

## See also

- <xref:System.Windows.Forms.DataGridView>
- [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Displaying Data in the Windows Forms DataGridView Control](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Data Display Modes in the Windows Forms DataGridView Control](data-display-modes-in-the-windows-forms-datagridview-control.md)

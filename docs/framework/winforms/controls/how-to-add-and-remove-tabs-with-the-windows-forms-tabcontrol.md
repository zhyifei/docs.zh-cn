---
title: "如何：使用 Windows 窗体 TabControl 添加和移除选项卡"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7df8b785b2c05acbbec9c17e12e462d755d0cd3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>如何：使用 Windows 窗体 TabControl 添加和移除选项卡
默认情况下，<xref:System.Windows.Forms.TabControl>控件包含两个<xref:System.Windows.Forms.TabPage>控件。 你可以访问通过这些选项卡<xref:System.Windows.Forms.TabControl.TabPages%2A>属性。  
  
### <a name="to-add-a-tab-programmatically"></a>以编程方式添加选项卡  
  
-   使用<xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>方法<xref:System.Windows.Forms.TabControl.TabPages%2A>属性。  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a>以编程方式移除一个选项卡  
  
-   若要删除所选的选项卡，使用<xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>方法<xref:System.Windows.Forms.TabControl.TabPages%2A>属性。  
  
     - 或 -  
  
-   若要删除的所有选项卡，使用<xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>方法<xref:System.Windows.Forms.TabControl.TabPages%2A>属性。  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [TabControl 控件概述](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [如何：向选项卡页添加控件](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [如何：禁用选项卡页](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [如何：更改 Windows 窗体 TabControl 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

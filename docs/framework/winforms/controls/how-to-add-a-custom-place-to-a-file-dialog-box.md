---
title: "如何：向文件对话框添加自定义区域"
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
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ce5efccfd2efda2f333b51868e375849f7c7752
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>如何：向文件对话框添加自定义区域
[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 上的默认打开和保存对话框在名为“收藏夹链接”的对话框左侧有一个区域。 此区域称为自定义区域。 <xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>类，可以添加到的文件夹<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>集合。  
  
> [!NOTE]
>  顺序显示在一个自定义位置<xref:System.Windows.Forms.OpenFileDialog>或<xref:System.Windows.Forms.SaveFileDialog>、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>属性必须设置为`true`（默认值）。  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>向文件对话框添加自定义区域  
  
-   添加路径，已知文件夹 GUID 或<xref:System.Windows.Forms.FileDialogCustomPlace>对象传递给<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>对话框中的集合。  
  
     以下代码示例演示了如何添加路径：  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [文件对话框自定义区域的已知文件夹 GUID](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)

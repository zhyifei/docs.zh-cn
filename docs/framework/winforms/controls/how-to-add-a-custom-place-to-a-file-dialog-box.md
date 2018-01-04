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
ms.workload: dotnet
ms.openlocfilehash: b1a10a58552dd416084da39838a9e36f15e85074
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="8f2db-102">如何：向文件对话框添加自定义区域</span><span class="sxs-lookup"><span data-stu-id="8f2db-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="8f2db-103">[!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] 上的默认打开和保存对话框在名为“收藏夹链接”的对话框左侧有一个区域。</span><span class="sxs-lookup"><span data-stu-id="8f2db-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="8f2db-104">此区域称为自定义区域。</span><span class="sxs-lookup"><span data-stu-id="8f2db-104">This area is called custom places.</span></span> <span data-ttu-id="8f2db-105"><xref:System.Windows.Forms.OpenFileDialog>和<xref:System.Windows.Forms.SaveFileDialog>类，可以添加到的文件夹<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="8f2db-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f2db-106">顺序显示在一个自定义位置<xref:System.Windows.Forms.OpenFileDialog>或<xref:System.Windows.Forms.SaveFileDialog>、<xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A>属性必须设置为`true`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="8f2db-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="8f2db-107">向文件对话框添加自定义区域</span><span class="sxs-lookup"><span data-stu-id="8f2db-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="8f2db-108">添加路径，已知文件夹 GUID 或<xref:System.Windows.Forms.FileDialogCustomPlace>对象传递给<xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>对话框中的集合。</span><span class="sxs-lookup"><span data-stu-id="8f2db-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="8f2db-109">以下代码示例演示了如何添加路径：</span><span class="sxs-lookup"><span data-stu-id="8f2db-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8f2db-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f2db-110">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="8f2db-111">文件对话框自定义区域的已知文件夹 GUID</span><span class="sxs-lookup"><span data-stu-id="8f2db-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)

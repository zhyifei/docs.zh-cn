---
title: "如何：应用 PropertyNameChanged 模式"
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
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe397a92ac6e79e84757baa0c41f6e0c54b7f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="7b577-102">如何：应用 PropertyNameChanged 模式</span><span class="sxs-lookup"><span data-stu-id="7b577-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="7b577-103">下面的代码示例演示如何应用*PropertyName*Changed 模式的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="7b577-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="7b577-104">实现与 Windows 窗体数据绑定引擎使用的自定义控件时，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="7b577-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b577-105">示例</span><span class="sxs-lookup"><span data-stu-id="7b577-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b577-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="7b577-106">Compiling the Code</span></span>  
 <span data-ttu-id="7b577-107">编译前面的代码示例：</span><span class="sxs-lookup"><span data-stu-id="7b577-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="7b577-108">将代码粘贴到空代码文件中。</span><span class="sxs-lookup"><span data-stu-id="7b577-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="7b577-109">你必须使用包含一个 Windows 窗体上的自定义控件`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="7b577-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b577-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b577-110">See Also</span></span>  
 [<span data-ttu-id="7b577-111">如何：实现 INotifyPropertyChanged 接口</span><span class="sxs-lookup"><span data-stu-id="7b577-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="7b577-112">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="7b577-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="7b577-113">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="7b577-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)

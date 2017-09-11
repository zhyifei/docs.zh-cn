---
title: "如何：在 Visual Basic 中检查连接状态"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Web connections
- IsAvailable property, about IsAvailable
- connections, checking status
- connection status
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3654eb51bb47317c2dc7bf74979a847438b0ae8
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="9b294-102">如何：在 Visual Basic 中检查连接状态</span><span class="sxs-lookup"><span data-stu-id="9b294-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="9b294-103"><xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> 属性可用于确定计算机是否具有有效的网络连接或 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="9b294-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="9b294-104">检查计算机是否具有有效的网络连接</span><span class="sxs-lookup"><span data-stu-id="9b294-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="9b294-105">确定 `IsAvailable` 属性是 `True` 还是 `False`。</span><span class="sxs-lookup"><span data-stu-id="9b294-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="9b294-106">以下代码检查属性的状态并进行报告：</span><span class="sxs-lookup"><span data-stu-id="9b294-106">The following code checks the property's status and reports it:</span></span>  
  
     <span data-ttu-id="9b294-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b294-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span></span>  
  
     <span data-ttu-id="9b294-108">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="9b294-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="9b294-109">它位于代码片段选取器的“连接和网络”中。</span><span class="sxs-lookup"><span data-stu-id="9b294-109">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="9b294-110">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="9b294-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b294-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b294-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>


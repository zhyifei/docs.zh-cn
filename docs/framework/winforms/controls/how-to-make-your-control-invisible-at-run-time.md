---
title: "如何：使控件在运行时不可见"
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
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 310750df0786eb07158909eb5e322369d157d1cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="0e68d-102">如何：使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="0e68d-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="0e68d-103">有的时候你可能想要创建用户控件在运行时不可见。</span><span class="sxs-lookup"><span data-stu-id="0e68d-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="0e68d-104">例如，用作闹钟控件可能除响警报时不可见。</span><span class="sxs-lookup"><span data-stu-id="0e68d-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="0e68d-105">这很容易实现通过设置<xref:System.Windows.Forms.Control.Visible%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0e68d-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="0e68d-106">如果<xref:System.Windows.Forms.Control.Visible%2A>属性是`true`，控件将显示为正常。</span><span class="sxs-lookup"><span data-stu-id="0e68d-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="0e68d-107">如果`false`，控件将被隐藏。</span><span class="sxs-lookup"><span data-stu-id="0e68d-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="0e68d-108">尽管在控件中的代码可能继续运行时不可见的你将不能与通过用户界面控件进行交互。</span><span class="sxs-lookup"><span data-stu-id="0e68d-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="0e68d-109">如果你想要创建的不可见的控件，仍可响应用户输入 （例如，鼠标单击），则应创建一个透明的控件。</span><span class="sxs-lookup"><span data-stu-id="0e68d-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="0e68d-110">有关详细信息，请参阅[使控件拥有透明背景](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)。</span><span class="sxs-lookup"><span data-stu-id="0e68d-110">For more information, see [Giving Your Control a Transparent Background](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="0e68d-111">要使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="0e68d-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="0e68d-112">将 <xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="0e68d-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0e68d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e68d-113">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Visible%2A>  
 [<span data-ttu-id="0e68d-114">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0e68d-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="0e68d-115">如何：为控件设置透明背景</span><span class="sxs-lookup"><span data-stu-id="0e68d-115">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)

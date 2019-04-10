---
title: 如何：使控件在运行时不可见
ms.date: 03/30/2017
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
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345893"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="4c3ca-102">如何：使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="4c3ca-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="4c3ca-103">有些的时候您可能想要创建在运行时是不可见的用户控件。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="4c3ca-104">例如，警报时钟控件可能不可见警报已响起时除外。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="4c3ca-105">这很容易实现： 设置<xref:System.Windows.Forms.Control.Visible%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="4c3ca-106">如果<xref:System.Windows.Forms.Control.Visible%2A>属性是`true`，控件将显示正常。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="4c3ca-107">如果`false`，将隐藏控件。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="4c3ca-108">尽管可能仍会在控件中的代码运行时不可见，则将不能与通过用户界面控件进行交互。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="4c3ca-109">如果你想要创建的不可见控件，仍会响应用户输入 （例如鼠标单击），则应创建透明控件。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="4c3ca-110">有关详细信息，请参阅[使控件拥有透明背景](how-to-give-your-control-a-transparent-background.md)。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="4c3ca-111">若要使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="4c3ca-111">To make your control invisible at run time</span></span>  
  
1. <span data-ttu-id="4c3ca-112">将 <xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4c3ca-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c3ca-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c3ca-113">See also</span></span>

- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="4c3ca-114">使用 .NET Framework 开发自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="4c3ca-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="4c3ca-115">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="4c3ca-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)

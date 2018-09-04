---
title: 如何：更改 Windows 窗体的边框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535876"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="3fe3f-102">如何：更改 Windows 窗体的边框</span><span class="sxs-lookup"><span data-stu-id="3fe3f-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="3fe3f-103">当确定 Windows 窗体的外观和行为时，有几种边框样式可供选择。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="3fe3f-104">通过更改 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性，可控制窗体调整大小的行为。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="3fe3f-105">此外，设置 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 会影响标题栏的显示方式以及其上出现的按钮布局。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="3fe3f-106">有关详细信息，请参阅<xref:System.Windows.Forms.FormBorderStyle>。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="3fe3f-107">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="3fe3f-108">另请参阅[如何： 更改 Windows 窗体使用设计器的边框](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="3fe3f-109">以编程方式设置 Windows 窗体的边框样式</span><span class="sxs-lookup"><span data-stu-id="3fe3f-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="3fe3f-110">将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为所需的样式。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="3fe3f-111">下面的代码示例设置窗体的边框样式`DlgBx1`到<xref:System.Windows.Forms.FormBorderStyle.FixedDialog>。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="3fe3f-112">另请参阅[如何： 在设计时创建对话框](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-112">Also see [How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="3fe3f-113">此外，如果已选择提供可选的窗体的边框样式**最小化**并**最大化**按钮，可以指定是否希望一个或两个这些按钮正常工作。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="3fe3f-114">当想要密切控制用户体验时，这些按钮会非常有用。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="3fe3f-115">**最小化**并**最大化**按钮默认启用，而且其功能操作通过**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="3fe3f-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe3f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe3f-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="3fe3f-117">Windows 窗体入门</span><span class="sxs-lookup"><span data-stu-id="3fe3f-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)

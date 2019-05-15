---
title: 如何：创建可重设大小的 Windows 窗体以供输入数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: 1b27c0e67aae1935c4216654d9f3ddf557719572
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588937"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a><span data-ttu-id="cfbe1-102">如何：创建可重设大小的 Windows 窗体以供输入数据</span><span class="sxs-lookup"><span data-stu-id="cfbe1-102">How to: Create a Resizable Windows Form for Data Entry</span></span>
<span data-ttu-id="cfbe1-103">良好的布局可以很好地响应其父窗体尺寸的更改。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-103">A good layout responds well to changes in the dimensions of its parent form.</span></span> <span data-ttu-id="cfbe1-104">可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件来安排窗体布局，从而以与窗体尺寸更改一致的方式调整和定位控件。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to arrange the layout of your form to resize and position your controls in a consistent way as the form's dimensions change.</span></span> <span data-ttu-id="cfbe1-105">当控件内容的更改引起布局更改时，<xref:System.Windows.Forms.TableLayoutPanel> 控件也会很有用。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-105">The <xref:System.Windows.Forms.TableLayoutPanel> control is also useful when changes in the contents of your controls cause changes in the layout.</span></span> <span data-ttu-id="cfbe1-106">可以在 Visual Studio 环境中完成此过程所涵盖的进程。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-106">The process covered in this procedure can be done within the Visual Studio environment.</span></span>  <span data-ttu-id="cfbe1-107">另请参阅[演练：创建数据输入可调整大小的 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-107">Also see [Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfbe1-108">示例</span><span class="sxs-lookup"><span data-stu-id="cfbe1-108">Example</span></span>  
 <span data-ttu-id="cfbe1-109">下面的示例演示当用户调整窗体大小时，如何使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件构建响应良好的布局。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-109">The following example demonstrates how to use a <xref:System.Windows.Forms.TableLayoutPanel> control to build a layout that responds well when the user resizes the form.</span></span> <span data-ttu-id="cfbe1-110">它还演示一个适合本地化的布局。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-110">It also demonstrates a layout that responds well to localization.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfbe1-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="cfbe1-111">Compiling the Code</span></span>  
 <span data-ttu-id="cfbe1-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cfbe1-112">This example requires:</span></span>  
  
- <span data-ttu-id="cfbe1-113">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="cfbe1-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfbe1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfbe1-114">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="cfbe1-115">如何：锚定和停靠在 TableLayoutPanel 控件中的子控件</span><span class="sxs-lookup"><span data-stu-id="cfbe1-115">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="cfbe1-116">如何：设计很好地响应本地化 Windows 窗体布局</span><span class="sxs-lookup"><span data-stu-id="cfbe1-116">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="cfbe1-117">Microsoft Windows 用户体验，用户界面开发人员和设计人员的官方指南。Redmond，WA:Microsoft Press，1999年。(USBN:0-7356-0566-1)</span><span class="sxs-lookup"><span data-stu-id="cfbe1-117">Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers. Redmond, WA: Microsoft Press, 1999. (USBN: 0-7356-0566-1)</span></span>](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)

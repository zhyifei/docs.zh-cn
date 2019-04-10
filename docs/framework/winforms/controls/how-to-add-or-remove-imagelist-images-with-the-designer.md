---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: b85b4d39235d49966b5f3c108986c8dd04bed5fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161520"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="f2a29-102">如何：使用设计器添加或移除 ImageList 图像</span><span class="sxs-lookup"><span data-stu-id="f2a29-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="f2a29-103">您可以将映像添加到<xref:System.Windows.Forms.ImageList>组件多种不同的方式。</span><span class="sxs-lookup"><span data-stu-id="f2a29-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="f2a29-104">您可以通过使用与关联的智能标记非常快速地添加图像<xref:System.Windows.Forms.ImageList>，或如果您在上设置多个其他属性<xref:System.Windows.Forms.ImageList>，可能会发现更方便地添加具有属性窗口的图像。</span><span class="sxs-lookup"><span data-stu-id="f2a29-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="f2a29-105">此外可以通过使用代码来添加映像。</span><span class="sxs-lookup"><span data-stu-id="f2a29-105">You can also add images by using code.</span></span> <span data-ttu-id="f2a29-106">有关如何通过代码添加图像的详细信息，请参阅[如何：添加或删除图像与 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f2a29-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="f2a29-107">通常填充<xref:System.Windows.Forms.ImageList>映像之前它是与控件相关联，但这不是必需组件。</span><span class="sxs-lookup"><span data-stu-id="f2a29-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2a29-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="f2a29-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f2a29-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="f2a29-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f2a29-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="f2a29-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="f2a29-111">若要添加或删除映像，通过使用属性窗口</span><span class="sxs-lookup"><span data-stu-id="f2a29-111">To add or remove images by using the Properties window</span></span>  
  
1.  <span data-ttu-id="f2a29-112">选择<xref:System.Windows.Forms.ImageList>组件，或添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="f2a29-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="f2a29-113">在属性窗口中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.ImageList.Images%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f2a29-113">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3.  <span data-ttu-id="f2a29-114">在中**图像集合编辑器**，单击**添加**或**删除**来添加或从列表中删除映像。</span><span class="sxs-lookup"><span data-stu-id="f2a29-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="f2a29-115">若要添加或删除使用智能标记的图像</span><span class="sxs-lookup"><span data-stu-id="f2a29-115">To add or remove images using the smart tag</span></span>  
  
1.  <span data-ttu-id="f2a29-116">选择<xref:System.Windows.Forms.ImageList>组件，或添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="f2a29-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="f2a29-117">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="f2a29-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3.  <span data-ttu-id="f2a29-118">在中**ImageList 任务**对话框中，选择**选择映像**。</span><span class="sxs-lookup"><span data-stu-id="f2a29-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4.  <span data-ttu-id="f2a29-119">在中**图像集合编辑器**单击**添加**或**删除**来添加或从列表中删除映像。</span><span class="sxs-lookup"><span data-stu-id="f2a29-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a29-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a29-120">See also</span></span>

- [<span data-ttu-id="f2a29-121">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="f2a29-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f2a29-122">演练：使用 Windows 窗体控件上的智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="f2a29-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="f2a29-123">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="f2a29-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)

---
title: 如何：使用设计器添加或移除 ImageList 图像
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 63692a797ad49f0adc3a0c5b0bfff1aebbc65257
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038267"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="31328-102">如何：使用设计器添加或移除 ImageList 图像</span><span class="sxs-lookup"><span data-stu-id="31328-102">How to: Add or Remove ImageList Images with the Designer</span></span>

<span data-ttu-id="31328-103">可以通过多种不同方式向<xref:System.Windows.Forms.ImageList>组件添加图像。</span><span class="sxs-lookup"><span data-stu-id="31328-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="31328-104">你可以通过使用与<xref:System.Windows.Forms.ImageList>关联的智能标记来非常快速地添加图像, 或者<xref:System.Windows.Forms.ImageList>, 如果你在上设置多个其他属性, 则可以更方便地使用属性窗口添加图像。</span><span class="sxs-lookup"><span data-stu-id="31328-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="31328-105">你还可以通过使用代码来添加映像。</span><span class="sxs-lookup"><span data-stu-id="31328-105">You can also add images by using code.</span></span> <span data-ttu-id="31328-106">有关如何添加包含代码的图像的详细信息, 请[参阅如何:添加或删除包含 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)的映像。</span><span class="sxs-lookup"><span data-stu-id="31328-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="31328-107">通常, 在<xref:System.Windows.Forms.ImageList>组件与控件关联之前, 使用图像填充组件, 但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="31328-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>


### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="31328-108">使用属性窗口添加或删除映像</span><span class="sxs-lookup"><span data-stu-id="31328-108">To add or remove images by using the Properties window</span></span>

1. <span data-ttu-id="31328-109"><xref:System.Windows.Forms.ImageList>选择组件, 或将其添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="31328-109">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="31328-110">在属性窗口中, 单击![ <xref:System.Windows.Forms.ImageList.Images%2A>属性旁边的省略号按钮 (Visual](./media/visual-studio-ellipsis-button.png)Studio 的属性窗口中的省略号按钮 (...)。</span><span class="sxs-lookup"><span data-stu-id="31328-110">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>

3. <span data-ttu-id="31328-111">在**图像集合编辑器**中, 单击 "**添加**" 或 "**删除**" 以添加或删除列表中的映像。</span><span class="sxs-lookup"><span data-stu-id="31328-111">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>

### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="31328-112">使用智能标记添加或删除图像</span><span class="sxs-lookup"><span data-stu-id="31328-112">To add or remove images using the smart tag</span></span>

1. <span data-ttu-id="31328-113"><xref:System.Windows.Forms.ImageList>选择组件, 或将其添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="31328-113">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>

2. <span data-ttu-id="31328-114">单击智能标记字形 (![智能标记字形](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="31328-114">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>

3. <span data-ttu-id="31328-115">在 " **ImageList 任务**" 对话框中, 选择 "**选择图像**"。</span><span class="sxs-lookup"><span data-stu-id="31328-115">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>

4. <span data-ttu-id="31328-116">在**图像集合编辑器**中, 单击 "**添加**" 或 "**删除**" 以添加或删除列表中的映像。</span><span class="sxs-lookup"><span data-stu-id="31328-116">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="31328-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="31328-117">See also</span></span>

- [<span data-ttu-id="31328-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="31328-118">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="31328-119">演练：使用 Windows 窗体控件上的智能标记执行常见任务</span><span class="sxs-lookup"><span data-stu-id="31328-119">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="31328-120">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="31328-120">ImageList Component</span></span>](imagelist-component-windows-forms.md)

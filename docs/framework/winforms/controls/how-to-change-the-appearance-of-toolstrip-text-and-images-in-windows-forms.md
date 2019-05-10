---
title: 如何：在 Windows 窗体中更改 ToolStrip 文本和图像的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: cf2f332b17bf6ff5b6ffb7cbc2d5777649728ec6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650846"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="77910-102">如何：在 Windows 窗体中更改 ToolStrip 文本和图像的外观</span><span class="sxs-lookup"><span data-stu-id="77910-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="77910-103">您可以控制是否在显示的文本和图像<xref:System.Windows.Forms.ToolStripItem>和它们相对于彼此的对齐方式和<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="77910-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="77910-104">若要定义 ToolStripItem 上显示的内容</span><span class="sxs-lookup"><span data-stu-id="77910-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="77910-105">设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="77910-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="77910-106">可能的值为`Image`， `ImageAndText`， `None`，和`Text`。</span><span class="sxs-lookup"><span data-stu-id="77910-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="77910-107">默认值为 `ImageAndText`。</span><span class="sxs-lookup"><span data-stu-id="77910-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="77910-108">若要使 ToolStripItem 上的文本对齐</span><span class="sxs-lookup"><span data-stu-id="77910-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="77910-109">设置<xref:System.Windows.Forms.ToolStripItem.TextAlign%2A>属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="77910-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="77910-110">可能的值为 top、 中间颜色和底部使用 left、 center 和右侧的任意组合。</span><span class="sxs-lookup"><span data-stu-id="77910-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="77910-111">默认值为 `MiddleCenter`。</span><span class="sxs-lookup"><span data-stu-id="77910-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="77910-112">若要对齐 ToolStripItem 上的图像</span><span class="sxs-lookup"><span data-stu-id="77910-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="77910-113">设置<xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="77910-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="77910-114">可能的值为 top、 中间颜色和底部使用 left、 center 和右侧的任意组合。</span><span class="sxs-lookup"><span data-stu-id="77910-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="77910-115">默认值为 `MiddleLeft`。</span><span class="sxs-lookup"><span data-stu-id="77910-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="77910-116">若要定义 ToolStripItem 文本和图像相对于彼此的显示方式</span><span class="sxs-lookup"><span data-stu-id="77910-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="77910-117">设置<xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="77910-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="77910-118">可能的值为`ImageAboveText`， `ImageBeforeText`， `Overlay`， `TextAboveImage`，和`TextBeforeImage`。</span><span class="sxs-lookup"><span data-stu-id="77910-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="77910-119">默认值为 `ImageBeforeText`。</span><span class="sxs-lookup"><span data-stu-id="77910-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="77910-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="77910-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="77910-121">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="77910-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="77910-122">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="77910-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="77910-123">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="77910-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)

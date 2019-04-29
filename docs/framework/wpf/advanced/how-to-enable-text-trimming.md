---
title: 如何：启用文本修整
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776102"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="4d75d-102">如何：启用文本修整</span><span class="sxs-lookup"><span data-stu-id="4d75d-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="4d75d-103">此示例演示使用情况和中的可用值的效果<xref:System.Windows.TextTrimming>枚举。</span><span class="sxs-lookup"><span data-stu-id="4d75d-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="4d75d-104">示例</span><span class="sxs-lookup"><span data-stu-id="4d75d-104">Example</span></span>

<span data-ttu-id="4d75d-105">下面的示例定义<xref:System.Windows.Controls.TextBlock>具有元素<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>属性设置。</span><span class="sxs-lookup"><span data-stu-id="4d75d-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="4d75d-106">设置相应<xref:System.Windows.TextTrimming>下面演示如何在代码中的属性。</span><span class="sxs-lookup"><span data-stu-id="4d75d-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="4d75d-107">有三个选项用于修整文本：**CharacterEllipsis**， **WordEllipsis**，和**None**。</span><span class="sxs-lookup"><span data-stu-id="4d75d-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="4d75d-108">当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**CharacterEllipsis**，文本进行修整，并使用靠近修整边缘的字符处省略号。</span><span class="sxs-lookup"><span data-stu-id="4d75d-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="4d75d-109">此设置旨在修整文本以使其更适应修整边界，但可能会导致某些单词仅部分修整。</span><span class="sxs-lookup"><span data-stu-id="4d75d-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="4d75d-110">下图显示了在此设置的效果<xref:System.Windows.Controls.TextBlock>类似于上面定义的一个。</span><span class="sxs-lookup"><span data-stu-id="4d75d-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="4d75d-111">![示例：TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="4d75d-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="4d75d-112">当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**WordEllipsis**，文本进行修整，并使用靠近修整边缘的第一个完整单词结尾处省略号。</span><span class="sxs-lookup"><span data-stu-id="4d75d-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="4d75d-113">此设置将不会显示单词部分修整，但通常不会修整那样靠近修整边缘作为文本**CharacterEllipsis**设置。</span><span class="sxs-lookup"><span data-stu-id="4d75d-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="4d75d-114">下图显示了在此设置的效果<xref:System.Windows.Controls.TextBlock>上面定义。</span><span class="sxs-lookup"><span data-stu-id="4d75d-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="4d75d-115">![示例：TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="4d75d-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="4d75d-116">当<xref:System.Windows.Controls.TextBlock.TextTrimming%2A>设置为**None**，会执行任何文本修整。</span><span class="sxs-lookup"><span data-stu-id="4d75d-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="4d75d-117">在这种情况下，只会将文本裁切到父文本容器的边界。</span><span class="sxs-lookup"><span data-stu-id="4d75d-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="4d75d-118">下图显示了在此设置的效果<xref:System.Windows.Controls.TextBlock>类似于上面定义的一个。</span><span class="sxs-lookup"><span data-stu-id="4d75d-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="4d75d-119">![示例：TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="4d75d-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>

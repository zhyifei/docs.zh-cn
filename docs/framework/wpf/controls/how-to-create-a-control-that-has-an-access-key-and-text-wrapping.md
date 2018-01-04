---
title: "如何：创建具有访问键和文本换行的控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 428d8febe5a789f22eef97301fca3aa4b22f25b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="869bd-102">如何：创建具有访问键和文本换行的控件</span><span class="sxs-lookup"><span data-stu-id="869bd-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="869bd-103">此示例演示如何创建具有访问键且支持文本换行的控件。</span><span class="sxs-lookup"><span data-stu-id="869bd-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="869bd-104">该示例使用<xref:System.Windows.Controls.Label>说明这些概念的控件。</span><span class="sxs-lookup"><span data-stu-id="869bd-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="869bd-105">示例</span><span class="sxs-lookup"><span data-stu-id="869bd-105">Example</span></span>  
 <span data-ttu-id="869bd-106">**将文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="869bd-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="869bd-107"><xref:System.Windows.Controls.Label>控件不支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="869bd-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="869bd-108">如果需要一个多次换行的标签，可以嵌套其他支持文本换行的元素，并将该元素放在标签内。</span><span class="sxs-lookup"><span data-stu-id="869bd-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="869bd-109">下面的示例演示如何使用<xref:System.Windows.Controls.TextBlock>进行包装若干行文本的标签。</span><span class="sxs-lookup"><span data-stu-id="869bd-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="869bd-110">**将访问键和文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="869bd-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="869bd-111">如果你需要<xref:System.Windows.Controls.Label>具有的访问密钥 （助记键），则使用<xref:System.Windows.Controls.AccessText>内的元素<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="869bd-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="869bd-112">控件如<xref:System.Windows.Controls.Label>， <xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.RadioButton>， <xref:System.Windows.Controls.CheckBox>， <xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Controls.TabItem>， <xref:System.Windows.Controls.Expander>，和<xref:System.Windows.Controls.GroupBox>具有默认控件模板。</span><span class="sxs-lookup"><span data-stu-id="869bd-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="869bd-113">这些模板包含<xref:System.Windows.Controls.ContentPresenter>。</span><span class="sxs-lookup"><span data-stu-id="869bd-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="869bd-114">您可以对设置的属性之一<xref:System.Windows.Controls.ContentPresenter>是<xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true"，可以用于指定控件的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="869bd-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="869bd-115">下面的示例演示如何创建<xref:System.Windows.Controls.Label>，它具有访问键，并支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="869bd-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="869bd-116">若要启用文本换行，该示例设置<xref:System.Windows.Controls.AccessText.TextWrapping%2A>属性并使用下划线字符指定访问密钥。</span><span class="sxs-lookup"><span data-stu-id="869bd-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="869bd-117">（紧跟下划线字符后面的字符就是访问键。）</span><span class="sxs-lookup"><span data-stu-id="869bd-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="869bd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="869bd-118">See Also</span></span>  
 [<span data-ttu-id="869bd-119">如何：设置 Label 的目标属性</span><span class="sxs-lookup"><span data-stu-id="869bd-119">How to: Set the Target Property of a Label</span></span>](http://msdn.microsoft.com/en-us/b24c6977-ebcb-4855-a9bb-3fd4435af8f8)

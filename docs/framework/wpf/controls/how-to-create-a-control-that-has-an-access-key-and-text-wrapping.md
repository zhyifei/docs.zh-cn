---
title: 如何：创建具有访问键和文本换行的控件
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: e410b92f90f775471ef5d89365549ccd5bb7f085
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361897"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="68d30-102">如何：创建具有访问键和文本换行的控件</span><span class="sxs-lookup"><span data-stu-id="68d30-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="68d30-103">此示例演示如何创建具有访问键且支持文本换行的控件。</span><span class="sxs-lookup"><span data-stu-id="68d30-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="68d30-104">该示例使用<xref:System.Windows.Controls.Label>控件来说明这些概念。</span><span class="sxs-lookup"><span data-stu-id="68d30-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68d30-105">示例</span><span class="sxs-lookup"><span data-stu-id="68d30-105">Example</span></span>  
 <span data-ttu-id="68d30-106">**将文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="68d30-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="68d30-107"><xref:System.Windows.Controls.Label>控件不支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="68d30-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="68d30-108">如果需要一个多次换行的标签，可以嵌套其他支持文本换行的元素，并将该元素放在标签内。</span><span class="sxs-lookup"><span data-stu-id="68d30-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="68d30-109">下面的示例演示如何使用<xref:System.Windows.Controls.TextBlock>进行包装若干行文本的标签。</span><span class="sxs-lookup"><span data-stu-id="68d30-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="68d30-110">**将访问键和文本换行添加到标签**</span><span class="sxs-lookup"><span data-stu-id="68d30-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="68d30-111">如果你需要<xref:System.Windows.Controls.Label>具有访问键 （助记键），请使用<xref:System.Windows.Controls.AccessText>内元素<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="68d30-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="68d30-112">控件，如<xref:System.Windows.Controls.Label>， <xref:System.Windows.Controls.Button>， <xref:System.Windows.Controls.RadioButton>， <xref:System.Windows.Controls.CheckBox>， <xref:System.Windows.Controls.MenuItem>， <xref:System.Windows.Controls.TabItem>， <xref:System.Windows.Controls.Expander>，和<xref:System.Windows.Controls.GroupBox>具有默认控件模板。</span><span class="sxs-lookup"><span data-stu-id="68d30-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="68d30-113">这些模板包含<xref:System.Windows.Controls.ContentPresenter>。</span><span class="sxs-lookup"><span data-stu-id="68d30-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="68d30-114">您可以设置的属性之一<xref:System.Windows.Controls.ContentPresenter>是<xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true"，这可用于指定控件的访问密钥。</span><span class="sxs-lookup"><span data-stu-id="68d30-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="68d30-115">下面的示例演示如何创建<xref:System.Windows.Controls.Label>的具有访问键且支持文本换行。</span><span class="sxs-lookup"><span data-stu-id="68d30-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="68d30-116">若要启用文本换行，该示例设置<xref:System.Windows.Controls.AccessText.TextWrapping%2A>属性，并使用下划线字符指定访问密钥。</span><span class="sxs-lookup"><span data-stu-id="68d30-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="68d30-117">（紧跟下划线字符后面的字符就是访问键。）</span><span class="sxs-lookup"><span data-stu-id="68d30-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="68d30-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="68d30-118">See also</span></span>
- <span data-ttu-id="68d30-119">[如何：设置标签的目标属性](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="68d30-119">[How to: Set the Target Property of a Label](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span></span>

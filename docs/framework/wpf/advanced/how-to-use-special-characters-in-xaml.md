---
title: 如何：在 XAML 中使用特殊字符
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051074"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="9a9cb-102">如何：在 XAML 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="9a9cb-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="9a9cb-103">在中创建的标记文件[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]自动保存在[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]utf-8 文件格式，这意味着大部分特殊字符，如重音符号进行正确编码。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="9a9cb-104">但是，有一组常用特殊字符的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="9a9cb-105">这些特殊字符采用[!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)]标准进行编码。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="9a9cb-106">下表显示这组特殊字符的编码语法：</span><span class="sxs-lookup"><span data-stu-id="9a9cb-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="9a9cb-107">字符</span><span class="sxs-lookup"><span data-stu-id="9a9cb-107">Character</span></span>|<span data-ttu-id="9a9cb-108">语法</span><span class="sxs-lookup"><span data-stu-id="9a9cb-108">Syntax</span></span>|<span data-ttu-id="9a9cb-109">描述</span><span class="sxs-lookup"><span data-stu-id="9a9cb-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="9a9cb-110">小于符号。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="9a9cb-111">大于符号。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="9a9cb-112">& 符号。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="9a9cb-113">"</span><span class="sxs-lookup"><span data-stu-id="9a9cb-113">"</span></span>|`&quot;`|<span data-ttu-id="9a9cb-114">双引号。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9a9cb-115">如果您创建标记文件使用文本编辑器中，如[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]记事本，您必须将文件保存在[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]utf-8 文件格式才能保留所有编码的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="9a9cb-116">以下示例演示创建标记时如何在文本中使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9a9cb-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a9cb-117">示例</span><span class="sxs-lookup"><span data-stu-id="9a9cb-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

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
ms.openlocfilehash: 27f2b18593d075b54eb8c3351bbb84415700cfd4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395808"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="3817a-102">如何：在 XAML 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="3817a-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="3817a-103">在 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 中创建的标记文件将自动保存为 Unicode UTF-8 文件格式，这意味着最特殊的字符（如重音符号）会正确编码。</span><span class="sxs-lookup"><span data-stu-id="3817a-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="3817a-104">但是，有一组常用特殊字符的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="3817a-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="3817a-105">这些特殊字符遵循 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] @no__t 标准进行编码。</span><span class="sxs-lookup"><span data-stu-id="3817a-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="3817a-106">下表显示这组特殊字符的编码语法：</span><span class="sxs-lookup"><span data-stu-id="3817a-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="3817a-107">字符</span><span class="sxs-lookup"><span data-stu-id="3817a-107">Character</span></span>|<span data-ttu-id="3817a-108">语法</span><span class="sxs-lookup"><span data-stu-id="3817a-108">Syntax</span></span>|<span data-ttu-id="3817a-109">描述</span><span class="sxs-lookup"><span data-stu-id="3817a-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="3817a-110">小于符号。</span><span class="sxs-lookup"><span data-stu-id="3817a-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="3817a-111">大于符号。</span><span class="sxs-lookup"><span data-stu-id="3817a-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="3817a-112">& 符号。</span><span class="sxs-lookup"><span data-stu-id="3817a-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="3817a-113">"</span><span class="sxs-lookup"><span data-stu-id="3817a-113">"</span></span>|`&quot;`|<span data-ttu-id="3817a-114">双引号。</span><span class="sxs-lookup"><span data-stu-id="3817a-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="3817a-115">如果使用文本编辑器（如 Windows 记事本）创建标记文件，则必须将该文件保存为 Unicode UTF-8 文件格式，以便保留所有编码的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3817a-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="3817a-116">以下示例演示创建标记时如何在文本中使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3817a-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3817a-117">示例</span><span class="sxs-lookup"><span data-stu-id="3817a-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

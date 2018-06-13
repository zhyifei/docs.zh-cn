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
ms.openlocfilehash: c593ca094487e8f7016b02870026321fbcb9a7c3
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256181"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="02e91-102">如何：在 XAML 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="02e91-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="02e91-103">在中创建的标记文件[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]自动保存在[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]utf-8 文件格式，这意味着大部分特殊字符，如重音符号进行正确编码。</span><span class="sxs-lookup"><span data-stu-id="02e91-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="02e91-104">但是，有一组常用特殊字符的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="02e91-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="02e91-105">这些特殊字符遵循[!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)]编码标准。</span><span class="sxs-lookup"><span data-stu-id="02e91-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="02e91-106">下表显示这组特殊字符的编码语法：</span><span class="sxs-lookup"><span data-stu-id="02e91-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="02e91-107">字符</span><span class="sxs-lookup"><span data-stu-id="02e91-107">Character</span></span>|<span data-ttu-id="02e91-108">语法</span><span class="sxs-lookup"><span data-stu-id="02e91-108">Syntax</span></span>|<span data-ttu-id="02e91-109">描述</span><span class="sxs-lookup"><span data-stu-id="02e91-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="02e91-110">小于符号。</span><span class="sxs-lookup"><span data-stu-id="02e91-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="02e91-111">大于符号。</span><span class="sxs-lookup"><span data-stu-id="02e91-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="02e91-112">& 符号。</span><span class="sxs-lookup"><span data-stu-id="02e91-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="02e91-113">"</span><span class="sxs-lookup"><span data-stu-id="02e91-113">"</span></span>|`&quot;`|<span data-ttu-id="02e91-114">双引号。</span><span class="sxs-lookup"><span data-stu-id="02e91-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="02e91-115">如果你创建的标记文件，使用文本编辑器中，如[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]记事本，你必须保存在文件[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]以保持任何 utf-8 文件格式编码的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="02e91-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="02e91-116">以下示例演示创建标记时如何在文本中使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="02e91-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02e91-117">示例</span><span class="sxs-lookup"><span data-stu-id="02e91-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

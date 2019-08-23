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
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918436"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="c565b-102">如何：在 XAML 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="c565b-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="c565b-103">中[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]创建的标记文件将自动[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]以 utf-8 文件格式保存, 这意味着, 最特殊的字符 (如重音符号) 已正确编码。</span><span class="sxs-lookup"><span data-stu-id="c565b-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="c565b-104">但是，有一组常用特殊字符的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="c565b-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="c565b-105">这些特殊字符遵循[!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)]编码的标准。</span><span class="sxs-lookup"><span data-stu-id="c565b-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="c565b-106">下表显示这组特殊字符的编码语法：</span><span class="sxs-lookup"><span data-stu-id="c565b-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="c565b-107">字符</span><span class="sxs-lookup"><span data-stu-id="c565b-107">Character</span></span>|<span data-ttu-id="c565b-108">语法</span><span class="sxs-lookup"><span data-stu-id="c565b-108">Syntax</span></span>|<span data-ttu-id="c565b-109">描述</span><span class="sxs-lookup"><span data-stu-id="c565b-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="c565b-110">小于符号。</span><span class="sxs-lookup"><span data-stu-id="c565b-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="c565b-111">大于符号。</span><span class="sxs-lookup"><span data-stu-id="c565b-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="c565b-112">& 符号。</span><span class="sxs-lookup"><span data-stu-id="c565b-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="c565b-113">"</span><span class="sxs-lookup"><span data-stu-id="c565b-113">"</span></span>|`&quot;`|<span data-ttu-id="c565b-114">双引号。</span><span class="sxs-lookup"><span data-stu-id="c565b-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="c565b-115">如果使用文本编辑器 (如 Windows 记事本) 创建标记文件, 则必须将该文件[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]保存为 utf-8 文件格式, 以便保留所有编码的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c565b-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="c565b-116">以下示例演示创建标记时如何在文本中使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c565b-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c565b-117">示例</span><span class="sxs-lookup"><span data-stu-id="c565b-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

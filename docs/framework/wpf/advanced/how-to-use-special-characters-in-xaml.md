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
# <a name="how-to-use-special-characters-in-xaml"></a>如何：在 XAML 中使用特殊字符
在 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 中创建的标记文件将自动保存为 Unicode UTF-8 文件格式，这意味着最特殊的字符（如重音符号）会正确编码。 但是，有一组常用特殊字符的处理方式不同。 这些特殊字符遵循 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] @no__t 标准进行编码。  
  
 下表显示这组特殊字符的编码语法：  
  
|字符|语法|描述|  
|---------------|------------|-----------------|  
|<|`&lt;`|小于符号。|  
|>|`&gt;`|大于符号。|  
|&|`&amp;`|& 符号。|  
|"|`&quot;`|双引号。|  
  
> [!NOTE]
> 如果使用文本编辑器（如 Windows 记事本）创建标记文件，则必须将该文件保存为 Unicode UTF-8 文件格式，以便保留所有编码的特殊字符。  
  
 以下示例演示创建标记时如何在文本中使用特殊字符。  
  
## <a name="example"></a>示例  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

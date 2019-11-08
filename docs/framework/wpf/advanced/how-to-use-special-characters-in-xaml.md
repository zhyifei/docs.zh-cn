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
ms.openlocfilehash: 59449637bb45f6b75462b6809c354af7972fc2e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740843"
---
# <a name="how-to-use-special-characters-in-xaml"></a>如何：在 XAML 中使用特殊字符
在 Visual Studio 中创建的标记文件将自动保存为 Unicode UTF-8 文件格式，这意味着，最特殊的字符（如重音符号）已正确编码。 但是，有一组常用特殊字符的处理方式不同。 这些特殊字符遵循用于编码的万维网联合会（W3C） XML 标准。  
  
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

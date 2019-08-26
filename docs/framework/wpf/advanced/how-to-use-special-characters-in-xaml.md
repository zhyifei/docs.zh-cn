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
# <a name="how-to-use-special-characters-in-xaml"></a>如何：在 XAML 中使用特殊字符
中[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]创建的标记文件将自动[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]以 utf-8 文件格式保存, 这意味着, 最特殊的字符 (如重音符号) 已正确编码。 但是，有一组常用特殊字符的处理方式不同。 这些特殊字符遵循[!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)]编码的标准。  
  
 下表显示这组特殊字符的编码语法：  
  
|字符|语法|描述|  
|---------------|------------|-----------------|  
|<|`&lt;`|小于符号。|  
|>|`&gt;`|大于符号。|  
|&|`&amp;`|& 符号。|  
|"|`&quot;`|双引号。|  
  
> [!NOTE]
> 如果使用文本编辑器 (如 Windows 记事本) 创建标记文件, 则必须将该文件[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]保存为 utf-8 文件格式, 以便保留所有编码的特殊字符。  
  
 以下示例演示创建标记时如何在文本中使用特殊字符。  
  
## <a name="example"></a>示例  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]

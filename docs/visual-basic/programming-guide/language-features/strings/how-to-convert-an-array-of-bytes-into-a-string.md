---
title: 如何：将一个字节数组转换成 Visual Basic 中的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 577cce6322bf80bf2abdb963f07938b1a8b5d174
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718346"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="6cecf-102">如何：将一个字节数组转换成 Visual Basic 中的字符串</span><span class="sxs-lookup"><span data-stu-id="6cecf-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="6cecf-103">本主题演示如何将字节从字节数组转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="6cecf-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cecf-104">示例</span><span class="sxs-lookup"><span data-stu-id="6cecf-104">Example</span></span>  
 <span data-ttu-id="6cecf-105">此示例使用<xref:System.Text.Encoding.GetString%2A>方法的<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>编码类将字节数组中的所有字节转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="6cecf-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 <span data-ttu-id="6cecf-106">您可以选择从多个编码选项，以字节数组转换为字符串：</span><span class="sxs-lookup"><span data-stu-id="6cecf-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
-   <span data-ttu-id="6cecf-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>：获取 ASCII（7 位）字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
-   <span data-ttu-id="6cecf-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>：获取使用 big endian 字节顺序的 utf-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
-   <span data-ttu-id="6cecf-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>：获取系统的当前 ANSI 代码页的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
-   <span data-ttu-id="6cecf-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>：获取使用 little-endian 字节顺序的 utf-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="6cecf-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>：获取使用 little-endian 字节顺序的 UTF-32 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
-   <span data-ttu-id="6cecf-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>：获取 UTF-7 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
-   <span data-ttu-id="6cecf-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>：获取 UTF-8 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="6cecf-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cecf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6cecf-114">See also</span></span>
- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="6cecf-115">如何：将字符串转换成 Visual Basic 中的字节数组</span><span class="sxs-lookup"><span data-stu-id="6cecf-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)

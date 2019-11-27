---
title: 如何：将字符串转换为字节数组
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 76fde3120ce629ce32f29ca28d90eba24fff726c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351969"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="bd9ec-102">如何：在 Visual Basic 中将字符串转换为字节数组</span><span class="sxs-lookup"><span data-stu-id="bd9ec-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="bd9ec-103">本主题演示如何将字符串转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd9ec-104">示例</span><span class="sxs-lookup"><span data-stu-id="bd9ec-104">Example</span></span>  
 <span data-ttu-id="bd9ec-105">此示例使用 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 编码类的 <xref:System.Text.Encoding.GetBytes%2A> 方法将字符串转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="bd9ec-106">可以从多个编码选项中进行选择，以将字符串转换为字节数组：</span><span class="sxs-lookup"><span data-stu-id="bd9ec-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="bd9ec-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>：获取 ASCII （7位）字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="bd9ec-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>：使用大字节序字节顺序获取 UTF-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="bd9ec-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>：获取系统的当前 ANSI 代码页的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="bd9ec-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>：获取使用小 endian 字节顺序的 UTF-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="bd9ec-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>：使用小字节序字节顺序获取 UTF-32 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="bd9ec-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>：获取 UTF-7 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="bd9ec-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>：获取 UTF-8 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="bd9ec-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9ec-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd9ec-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="bd9ec-115">如何：在 Visual Basic 中将字节数组转换为字符串</span><span class="sxs-lookup"><span data-stu-id="bd9ec-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)

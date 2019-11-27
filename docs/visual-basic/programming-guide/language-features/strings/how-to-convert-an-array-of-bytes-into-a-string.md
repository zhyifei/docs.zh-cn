---
title: 如何：将字节数组转换为字符串
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 8c1d9d1d2e89390873bc1c3dbb9623f047433a9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351976"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="ccb83-102">如何：在 Visual Basic 中将字节数组转换为字符串</span><span class="sxs-lookup"><span data-stu-id="ccb83-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="ccb83-103">本主题说明如何将字节数组中的字节转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="ccb83-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb83-104">示例</span><span class="sxs-lookup"><span data-stu-id="ccb83-104">Example</span></span>  
 <span data-ttu-id="ccb83-105">此示例使用 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 编码类的 <xref:System.Text.Encoding.GetString%2A> 方法将字节数组中的所有字节转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="ccb83-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="ccb83-106">可以从多个编码选项中进行选择，将字节数组转换为字符串：</span><span class="sxs-lookup"><span data-stu-id="ccb83-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="ccb83-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>：获取 ASCII （7位）字符集的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="ccb83-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>：使用大字节序字节顺序获取 UTF-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb83-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>：获取系统的当前 ANSI 代码页的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="ccb83-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>：获取使用小 endian 字节顺序的 UTF-16 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb83-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>：使用小字节序字节顺序获取 UTF-32 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ccb83-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>：获取 UTF-7 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="ccb83-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>：获取 UTF-8 格式的编码。</span><span class="sxs-lookup"><span data-stu-id="ccb83-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb83-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccb83-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="ccb83-115">如何：在 Visual Basic 中将字符串转换为字节数组</span><span class="sxs-lookup"><span data-stu-id="ccb83-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)

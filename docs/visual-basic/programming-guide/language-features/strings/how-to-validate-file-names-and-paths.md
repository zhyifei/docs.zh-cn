---
title: 如何：在 Visual Basic 中验证文件名和路径
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647799"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="0fff0-102">如何：在 Visual Basic 中验证文件名和路径</span><span class="sxs-lookup"><span data-stu-id="0fff0-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="0fff0-103">此示例返回`Boolean`值，该值指示字符串是否表示文件名称或路径。</span><span class="sxs-lookup"><span data-stu-id="0fff0-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="0fff0-104">如果名称包含不允许的文件系统的字符的验证检查。</span><span class="sxs-lookup"><span data-stu-id="0fff0-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fff0-105">示例</span><span class="sxs-lookup"><span data-stu-id="0fff0-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="0fff0-106">此示例不会检查，如果未冒号或不具有名称的目录位置名称，不正确或名称的长度超过了系统定义的最大长度。</span><span class="sxs-lookup"><span data-stu-id="0fff0-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="0fff0-107">它也不会检查应用程序是否具有指定名称的文件系统资源的访问权。</span><span class="sxs-lookup"><span data-stu-id="0fff0-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fff0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fff0-108">See Also</span></span>  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [<span data-ttu-id="0fff0-109">在 Visual Basic 中验证字符串</span><span class="sxs-lookup"><span data-stu-id="0fff0-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

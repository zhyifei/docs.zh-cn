---
title: XML 注释异常必须具有“cref”特性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592031"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="170aa-102">XML 注释异常必须具有“cref”特性</span><span class="sxs-lookup"><span data-stu-id="170aa-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="170aa-103">@No__t-0exception > 标记提供了一种方法来记录可由方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="170aa-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="170aa-104">必需的 `cref` 特性指定了文档生成器检查的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="170aa-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="170aa-105">如果该成员存在，则将其转换为文档文件中的规范元素名称。</span><span class="sxs-lookup"><span data-stu-id="170aa-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="170aa-106">**错误 ID：** BC42319</span><span class="sxs-lookup"><span data-stu-id="170aa-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="170aa-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="170aa-107">To correct this error</span></span>  
  
- <span data-ttu-id="170aa-108">将 `cref` 特性添加到异常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="170aa-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    <span data-ttu-id="170aa-109">xml</span><span class="sxs-lookup"><span data-stu-id="170aa-109">xml</span></span>  
    <span data-ttu-id="170aa-110">"" "<exception cref="member">说明</exception></span><span class="sxs-lookup"><span data-stu-id="170aa-110">'''<exception cref="member">description</exception></span></span>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)

---
title: XML 注释异常必须具有“cref”特性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321177"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="33afb-102">XML 注释异常必须具有“cref”特性</span><span class="sxs-lookup"><span data-stu-id="33afb-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="33afb-103">@No__t_0exception 的 > 标记提供了一种方法来记录可由方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="33afb-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="33afb-104">必需 `cref` 特性指定了文档生成器检查的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="33afb-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="33afb-105">如果该成员存在，则将其转换为文档文件中的规范元素名称。</span><span class="sxs-lookup"><span data-stu-id="33afb-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="33afb-106">**错误 ID：** BC42319</span><span class="sxs-lookup"><span data-stu-id="33afb-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="33afb-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="33afb-107">To correct this error</span></span>

<span data-ttu-id="33afb-108">将 `cref` 特性添加到异常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="33afb-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="33afb-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="33afb-109">See also</span></span>

- [<span data-ttu-id="33afb-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="33afb-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="33afb-111">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="33afb-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="33afb-112">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="33afb-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

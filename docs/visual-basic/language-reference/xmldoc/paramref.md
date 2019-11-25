---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 78227a17584271f91283198e95f5aa389b3ef14b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352283"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="dac4e-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dac4e-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="dac4e-102">Formats a word as a parameter.</span><span class="sxs-lookup"><span data-stu-id="dac4e-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac4e-103">语法</span><span class="sxs-lookup"><span data-stu-id="dac4e-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="dac4e-104">参数</span><span class="sxs-lookup"><span data-stu-id="dac4e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dac4e-105">要引用的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="dac4e-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="dac4e-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="dac4e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dac4e-107">备注</span><span class="sxs-lookup"><span data-stu-id="dac4e-107">Remarks</span></span>  
 <span data-ttu-id="dac4e-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span><span class="sxs-lookup"><span data-stu-id="dac4e-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="dac4e-109">The XML file can be processed to format this parameter in some distinct way.</span><span class="sxs-lookup"><span data-stu-id="dac4e-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="dac4e-110">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="dac4e-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dac4e-111">示例</span><span class="sxs-lookup"><span data-stu-id="dac4e-111">Example</span></span>  
 <span data-ttu-id="dac4e-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span><span class="sxs-lookup"><span data-stu-id="dac4e-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="dac4e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dac4e-113">See also</span></span>

- [<span data-ttu-id="dac4e-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="dac4e-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

---
title: <para> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524743"
---
# <a name="para-visual-basic"></a><span data-ttu-id="e9aff-102">\<para > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="e9aff-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="e9aff-103">指定将内容的格式设置为段落。</span><span class="sxs-lookup"><span data-stu-id="e9aff-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9aff-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9aff-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9aff-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9aff-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="e9aff-106">段落文本。</span><span class="sxs-lookup"><span data-stu-id="e9aff-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9aff-107">备注</span><span class="sxs-lookup"><span data-stu-id="e9aff-107">Remarks</span></span>  
 <span data-ttu-id="e9aff-108">@No__t_0 标记在标记内使用，如[\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)、 [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md)或[\<returns](../../../visual-basic/language-reference/xmldoc/returns.md)>，并允许向文本中添加结构。</span><span class="sxs-lookup"><span data-stu-id="e9aff-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="e9aff-109">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="e9aff-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9aff-110">示例</span><span class="sxs-lookup"><span data-stu-id="e9aff-110">Example</span></span>  
 <span data-ttu-id="e9aff-111">此示例使用 `<para>` 标记将 `UpdateRecord` 方法的备注部分拆分为两个段落。</span><span class="sxs-lookup"><span data-stu-id="e9aff-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e9aff-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9aff-112">See also</span></span>

- [<span data-ttu-id="e9aff-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="e9aff-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)

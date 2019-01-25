---
title: 如何：使实体可序列化
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 9b4ff81b4a779b474097de1a69e65f4864e08691
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604201"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="ef9a5-102">如何：使实体可序列化</span><span class="sxs-lookup"><span data-stu-id="ef9a5-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="ef9a5-103">当你生成代码时，可以使实体可序列化。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="ef9a5-104">实体类使用 <xref:System.Runtime.Serialization.DataContractAttribute> 属性修饰，列使用 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性修饰。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="ef9a5-105">使用 Visual Studio 的开发人员可以使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="ef9a5-106">如果使用 SQLMetal 命令行工具，使用 **/serialization**选项与`unidirectional`参数。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="ef9a5-107">有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef9a5-108">示例</span><span class="sxs-lookup"><span data-stu-id="ef9a5-108">Example</span></span>  
 <span data-ttu-id="ef9a5-109">以下 SQLMetal 命令行会产生包含可序列化实体的文件。</span><span class="sxs-lookup"><span data-stu-id="ef9a5-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef9a5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef9a5-110">See also</span></span>
- [<span data-ttu-id="ef9a5-111">序列化</span><span class="sxs-lookup"><span data-stu-id="ef9a5-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [<span data-ttu-id="ef9a5-112">创建对象模型</span><span class="sxs-lookup"><span data-stu-id="ef9a5-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)

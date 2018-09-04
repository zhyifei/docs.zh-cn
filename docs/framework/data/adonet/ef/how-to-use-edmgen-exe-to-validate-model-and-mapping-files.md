---
title: 如何：使用 EdmGen.exe 验证模型和映射文件
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: fda8698381e98c64318f1a26f77f0263e9085074
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512440"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="3f41a-102">如何：使用 EdmGen.exe 验证模型和映射文件</span><span class="sxs-lookup"><span data-stu-id="3f41a-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="3f41a-103">本主题演示如何使用[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)工具验证模型和映射文件。</span><span class="sxs-lookup"><span data-stu-id="3f41a-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="3f41a-104">有关详细信息，请参阅[实体数据模型](../../../../../docs/framework/data/adonet/entity-data-model.md)。</span><span class="sxs-lookup"><span data-stu-id="3f41a-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="3f41a-105">使用 EdmGen.exe 验证 School 模型</span><span class="sxs-lookup"><span data-stu-id="3f41a-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="3f41a-106">创建 School 数据库。</span><span class="sxs-lookup"><span data-stu-id="3f41a-106">Create the School database.</span></span> <span data-ttu-id="3f41a-107">有关详细信息，请参阅[创建 School 示例数据库](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。</span><span class="sxs-lookup"><span data-stu-id="3f41a-107">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="3f41a-108">生成 School 模型。</span><span class="sxs-lookup"><span data-stu-id="3f41a-108">Generate the School model.</span></span> <span data-ttu-id="3f41a-109">有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。</span><span class="sxs-lookup"><span data-stu-id="3f41a-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="3f41a-110">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="3f41a-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f41a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f41a-111">See Also</span></span>  
 [<span data-ttu-id="3f41a-112">如何： 手动配置实体框架项目</span><span class="sxs-lookup"><span data-stu-id="3f41a-112">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="3f41a-113">ADO.NET 实体数据模型工具</span><span class="sxs-lookup"><span data-stu-id="3f41a-113">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="3f41a-114">如何： 预生成视图以提高查询性能</span><span class="sxs-lookup"><span data-stu-id="3f41a-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="3f41a-115">如何：使用 EdmGen.exe 生成对象层代码</span><span class="sxs-lookup"><span data-stu-id="3f41a-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

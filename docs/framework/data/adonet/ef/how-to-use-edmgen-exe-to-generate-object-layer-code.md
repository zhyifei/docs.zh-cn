---
title: 如何：使用 EdmGen.exe 生成对象层代码
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 8a39027ee6a5647bbd645f5a38e35d61f7ebbd8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61605764"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="ad36a-102">如何：使用 EdmGen.exe 生成对象层代码</span><span class="sxs-lookup"><span data-stu-id="ad36a-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="ad36a-103">本主题演示如何使用[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)工具来生成对象层代码基于.csdl 文件。</span><span class="sxs-lookup"><span data-stu-id="ad36a-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="ad36a-104">使用 EdmGen.exe 为 Visual Basic 项目的 School 模型生成对象层代码</span><span class="sxs-lookup"><span data-stu-id="ad36a-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="ad36a-105">创建 School 数据库。</span><span class="sxs-lookup"><span data-stu-id="ad36a-105">Create the School database.</span></span> <span data-ttu-id="ad36a-106">有关详细信息，请参阅[创建 School 示例数据库](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="ad36a-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="ad36a-107">生成 School 模型或获取 School.csdl 文件。</span><span class="sxs-lookup"><span data-stu-id="ad36a-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="ad36a-108">有关详细信息，请参阅[如何：使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ad36a-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="ad36a-109">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="ad36a-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="ad36a-110">使用 EdmGen.exe 为 C# 项目的 School 模型生成对象层代码</span><span class="sxs-lookup"><span data-stu-id="ad36a-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="ad36a-111">创建 School 数据库。</span><span class="sxs-lookup"><span data-stu-id="ad36a-111">Create the School database.</span></span> <span data-ttu-id="ad36a-112">有关详细信息，请参阅[创建 School 示例数据库](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="ad36a-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="ad36a-113">生成 School 模型或获取 School.csdl 文件。</span><span class="sxs-lookup"><span data-stu-id="ad36a-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="ad36a-114">有关详细信息，请参阅[如何：使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ad36a-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="ad36a-115">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="ad36a-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ad36a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad36a-116">See also</span></span>

- [<span data-ttu-id="ad36a-117">建模和映射</span><span class="sxs-lookup"><span data-stu-id="ad36a-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- <span data-ttu-id="ad36a-118">[如何：手动配置实体框架项目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad36a-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="ad36a-119">[ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad36a-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="ad36a-120">[如何：预生成视图以提高查询性能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad36a-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="ad36a-121">如何：使用 EdmGen.exe 生成模型和映射文件</span><span class="sxs-lookup"><span data-stu-id="ad36a-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

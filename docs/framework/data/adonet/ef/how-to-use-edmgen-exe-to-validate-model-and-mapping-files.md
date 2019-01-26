---
title: 如何：使用 EdmGen.exe 验证模型和映射文件
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 87150aee8eac6a594b18b77230889c1208003dde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566354"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>如何：使用 EdmGen.exe 验证模型和映射文件
本主题演示如何使用[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)工具验证模型和映射文件。 有关详细信息，请参阅[实体数据模型](../../../../../docs/framework/data/adonet/entity-data-model.md)。  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>使用 EdmGen.exe 验证 School 模型  
  
1.  创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。  
  
2.  生成 School 模型。 有关详细信息，请参阅[如何：使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。  
  
3.  在命令提示符下执行以下命令（无换行符）：  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>请参阅
- [如何：手动配置实体框架项目](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [ADO.NET 实体数据模型工具](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [如何：预生成视图以提高查询性能](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [如何：使用 EdmGen.exe 生成对象层代码](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

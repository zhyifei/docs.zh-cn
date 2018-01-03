---
title: "如何：使用 EdmGen.exe 生成对象层代码"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dd5c8f578e6e3f0816dff06909a44d80a1c0fd57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>如何：使用 EdmGen.exe 生成对象层代码
本主题演示如何使用[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)工具生成对象层代码基于.csdl 文件。  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>使用 EdmGen.exe 为 Visual Basic 项目的 School 模型生成对象层代码  
  
1.  创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。  
  
2.  生成 School 模型或获取 School.csdl 文件。 有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。  
  
3.  在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>使用 EdmGen.exe 为 C# 项目的 School 模型生成对象层代码  
  
1.  创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。  
  
2.  生成 School 模型或获取 School.csdl 文件。 有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。  
  
3.  在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>请参阅  
 [建模和映射](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [如何： 手动配置实体框架项目](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [ADO.NET 实体数据模型工具](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [如何： 预生成视图来提高查询性能](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [如何：使用 EdmGen.exe 生成模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

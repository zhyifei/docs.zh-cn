---
title: 如何：使实体可序列化
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002710"
---
# <a name="how-to-make-entities-serializable"></a>如何：使实体可序列化
当您生成代码时，可以使实体可序列化。 实体类使用 <xref:System.Runtime.Serialization.DataContractAttribute> 属性修饰，列使用 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性修饰。  
  
 使用 Visual Studio 的开发人员可以使用对象关系设计器来实现此目的。  
  
 如果使用 SQLMetal 命令行工具，请将 **/serialization**选项与 `unidirectional` 参数一起使用。 有关详细信息，请参阅 [SqlMetal.exe（代码生成工具）](../../../../tools/sqlmetal-exe-code-generation-tool.md)。  
  
## <a name="example"></a>示例  
 以下 SQLMetal 命令行会产生包含可序列化实体的文件。  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>另请参阅

- [序列化](serialization.md)
- [创建对象模型](creating-the-object-model.md)

---
title: 建模和映射
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 33064d35b7ac4c469df3ca6f0111cc84ef10eb08
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248490"
---
# <a name="modeling-and-mapping"></a>建模和映射
在[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中，可以采用最适合您应用程序的方式定义概念模型、存储模型以及这两种模型之间的映射。 使用 Visual Studio 中的实体数据模型工具可创建。数据库或图形模型中的[edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))，然后在数据库或模型发生更改时更新该文件。  
  
 实体框架4.1 开始，还可使用 Code First 开发以编程方式创建模型。 对于 Code First 开发，有两种不同的方案。 在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。  
  
 有关详细信息，请参阅[创建和映射概念模型](https://go.microsoft.com/fwlink/?LinkId=235016)。  
  
 你还可以使用 .NET Framework 附带的 EDM 生成器。 EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。 也可以手动创建模型和映射内容。 有关详细信息，请参阅[EDM 生成器（edmgen.exe）](edm-generator-edmgen-exe.md)。

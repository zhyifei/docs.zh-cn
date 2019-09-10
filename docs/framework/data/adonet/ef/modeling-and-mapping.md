---
title: 建模和映射
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 133539ab1b6d6f2f0ab3f8deed5b22240c2bb07e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854401"
---
# <a name="modeling-and-mapping"></a>建模和映射
在实体框架中，可以定义概念模型、存储模型以及这两者之间的映射，以最适合应用程序的方式进行。 使用 Visual Studio 中的实体数据模型工具可创建。数据库或图形模型中的[edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))，然后在数据库或模型发生更改时更新该文件。  
  
 实体框架4.1 开始，还可使用 Code First 开发以编程方式创建模型。 对于 Code First 开发，有两种不同的方案。 在两种情况下，开发人员通过对 .NET Framework 类定义进行编码来定义模型，然后可选择使用数据注释或 fluent API 指定其他映射或配置。  
  
 有关详细信息，请参阅[创建和映射概念模型](https://go.microsoft.com/fwlink/?LinkId=235016)。  
  
 你还可以使用 .NET Framework 附带的 EDM 生成器。 EdmGen.exe 从现有数据源生成 .csdl、 .ssdl 和 .msl 文件。 也可以手动创建模型和映射内容。 有关详细信息，请参阅[EDM 生成器（edmgen.exe）](edm-generator-edmgen-exe.md)。

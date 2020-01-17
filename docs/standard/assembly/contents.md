---
title: 程序集内容
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: bee9d5422ec3101b2486f233ae0816ae3643f4e7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345577"
---
# <a name="assembly-contents"></a>程序集内容

通常，静态程序集可能由以下四个元素组成：

- [程序集清单](manifest.md)，包含程序集元数据。

- 类型元数据。  

- 实现这些类型的 Microsoft 中间语言 (MSIL) 代码。 它由编译器从一个或多个源代码文件生成。

- [资源](../../framework/resources/index.md)集。  

只有程序集清单是必需的，但也需要类型或资源来向程序集提供任何有意义的功能。

下图显示分组到单个物理文件中的这些元素：

![名为 MyAssembly.dll 的单文件程序集](./media/contents/single-file-assembly.gif)

设计源代码时，你会作出有关如何将应用程序的功能划分到一个或多个文件的明确的决定。 在设计 .NET 代码时，你也将作出类似的决定，即如何将应用程序的功能划分到一个或多个程序集中。

## <a name="see-also"></a>请参阅

- [.NET 中的程序集](index.md)
- [程序集清单](manifest.md)
- [程序集安全注意事项](security-considerations.md)

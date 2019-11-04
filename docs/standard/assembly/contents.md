---
title: 程序集内容
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- assemblies [.NET Core]
- single-file assemblies
- multifile assemblies [.NET Framework]
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 9ca12ee4bd993db3dd200a3b340c220ce5188796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122536"
---
# <a name="assembly-contents"></a>程序集内容
通常，静态程序集可能由以下四个元素组成：

- [程序集清单](manifest.md)，包含程序集元数据。

- 类型元数据。  

- 实现这些类型的 Microsoft 中间语言 (MSIL) 代码。 它由编译器从一个或多个源代码文件生成。

- 资源集。  

只有程序集清单是必需的，但也需要类型或资源来向程序集提供任何有意义的功能。

下图显示分组到单个物理文件中的这些元素。

![显示名为 MyAssembly.dll 的单文件程序集的图表。](./media/contents/single-file-assembly.gif)

在此插图中，所有三个文件均属于一个程序集，如 MyAssembly.dll 所包含的程序集清单文件中所述。 对于该文件系统，这三个文件是三个独立的文件。 请注意，文件 Util.netmodule 被编译为一个模块，因为它不包含任何程序集信息。 创建程序集之后，已将该程序集清单添加到指示程序集与 Util.netmodule 和 Graphic.bmp 之间关系的 MyAssembly.dll 中。

现在设计源代码时，你会作出有关如何将应用程序的功能划分到一个或多个文件的明确的决定。 在设计 .NET Framework 代码时，你也将作出类似的决定，即如何将应用程序的功能划分到一个或多个程序集中。

## <a name="see-also"></a>请参阅

- [.NET 中的程序集](index.md)
- [程序集清单](manifest.md)
- [程序集安全注意事项](security-considerations.md)

---
title: COM 互操作介绍 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 639b621215f25bc1042274a92a21fca2985e5918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644389"
---
# <a name="introduction-to-com-interop-visual-basic"></a>COM 互操作介绍 (Visual Basic)
组件对象模型 (COM) 允许到其他组件和承载应用程序公开其功能的对象。 COM 对象进行了 Windows 编程多年的基础，而应用程序面向公共语言运行时 (CLR) 提供了许多优点。  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] com 开发的那些，最终将取代应用程序 到那时，你可能需要使用或通过使用 Visual Studio 创建 COM 对象。 与 COM 互操作性或*COM 互操作*，使你能够使用现有的 COM 对象时转换到[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]在自己的进度。  
  
 通过使用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]若要创建 COM 组件，你可以使用免注册 COM 互操作。 这使您控制当多个版本的计算机上，安装并允许最终用户使用 XCOPY 或 FTP 将复制到其计算机上的相应目录的应用程序可以运行它的位置时，才启用哪个 DLL 版本。 有关详细信息，请参阅[免注册 COM 互操作](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)。  
  
## <a name="managed-code-and-data"></a>托管的代码和数据  
 有关开发代码[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]称为*托管代码*，并包含由 CLR 的元数据。 使用的数据[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序称为*托管的数据*因为运行时管理数据相关的任务，比如分配和回收内存以及执行类型检查。 默认情况下，Visual Basic.NET 中使用托管的代码和数据，但你可以访问非托管的代码和 COM 对象使用互操作程序集 （后面将介绍在此页上） 的数据。  
  
## <a name="assemblies"></a>程序集  
 程序集是主要构建基块的[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。 它是功能的一个已生成、 版本控制的并作为单个实现单元包含一个或多个文件已部署的集合。 每个程序集包含程序集清单。  
  
## <a name="type-libraries-and-assembly-manifests"></a>类型库和程序集清单  
 类型库描述的 COM 对象，例如成员名称和数据类型的特征。 程序集清单执行的相同函数[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。 它们包括以下信息：  
  
-   程序集标识、 版本、 区域性和数字签名。  
  
-   构成程序集实现的文件。  
  
-   类型和构成该程序集的资源。 这包括那些从其导出。  
  
-   编译时对其他程序集的依赖关系。  
  
-   要正确运行的程序集所需的权限。  
  
 有关程序集和程序集清单的详细信息，请参阅[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)。  
  
### <a name="importing-and-exporting-type-libraries"></a>导入和导出类型库  
 Visual Studio 包含一个实用工具，Tlbimp，它允许你从类型库到导入信息[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。 通过使用 Tlbexp 实用程序，可以从程序集生成类型库。  
  
 有关 Tlbimp 和 Tlbexp 的信息，请参阅[Tlbimp.exe （类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)和[Tlbexp.exe （类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)。  
  
## <a name="interop-assemblies"></a>互操作程序集  
 互操作程序集是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]代码的桥之间托管和非托管的程序集，映射到等效的 COM 对象成员[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]管理成员。 Visual Basic.net 创建的互操作程序集处理的许多使用 COM 对象，如互操作封送处理的详细信息。  
  
## <a name="interoperability-marshaling"></a>互操作封送处理  
 所有[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序共享的一组启用的对象，而不考虑使用的编程语言的互操作性的常见类型。 参数和返回值的 COM 对象有时使用不同于在托管代码中使用的数据类型。 *互操作封送处理*是打包参数和返回值为等效的数据类型的过程，因为它们移动到和从 COM 对象。 有关详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。  
  
## <a name="see-also"></a>请参阅  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)  
 [演练：使用 COM 对象实现继承](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [与非托管代码交互操作](../../../framework/interop/index.md)  
 [互操作性疑难解答](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Tlbimp.exe（类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe（类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [互操作封送处理](../../../framework/interop/interop-marshaling.md)  
 [免注册 COM 互操作](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)

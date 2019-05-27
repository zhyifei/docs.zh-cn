---
title: .NET Native 一般疑难解答
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca0f093e85a5ac983266ba34f78021d6af6018c0
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052036"
---
# <a name="net-native-general-troubleshooting"></a>.NET Native 一般疑难解答
本主题介绍如何使用.NET Native 开发应用程序时可能遇到的潜在问题进行疑难解答。  
  
- **问题：** 你的生成输出窗口不会正确更新。  
  
     **解决方法：** 在生成完成之前，不会更新该生成输出窗口。 生成时间可能会长达数分钟，因此在可能看到更新之前可能会有一个延误。  
  
- **问题：** 增加应用的 ARM 零售生成时间。  
  
     **解决方法：** 应用程序部署到 ARM 设备时，会调用.NET Native 的基础结构。 该编译执行了大量的优化，同时还确保反射等非静态语义继续工作。 此外，.NET 框架中应用使用的那部分得到动态链接，以达到最佳性能，并且还必须编译到本机代码之中。 这就是编译花费时间较长的原因。  
  
     然而，对于标准开发机器上的大多数应用而言，标准编译的编译时间仍在一分钟以内。  通常，在标准开发机器上仅为 .NET Framework 生成本机映像就要花上数分钟。  即使所有的优化可改善生成的代码并且包含 .NET 框架，应用版本时间通常要花费一两分钟。  
  
     我们将继续工作，通过调查多线程编译和其他优化方法来提升编译性能。  
  
- **问题：** 你不知道使用.NET Native 编译你的应用程序。  
  
     **解决方法：** 如果在调用.NET Native 编译器，您会发现更长的生成时间和任务管理器将显示各种.NET 本机组件进程，如 ILC.exe 和 nutc_driver.exe。  
  
     已成功生成使用.NET Native 项目后，您会发现 obj 下，输出\\*config*\ *arch*\\*projectname*.ilc\out 目录。最终本机包内容可在 bin\\*arch*\\*config*\AppX 目录下找到。 如果已部署该应用，最终本机包内容位于 \bin\\arch\\config\AppX 目录下。  
  
- **问题：**.NET Native 编译应用程序正在引发运行时异常 (通常[丢失元数据异常](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)或[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)异常)，它未引发时无需编译。NET 本机。  
  
     **解决方法：** 因为.NET Native 未提供的元数据或通过反射可用的实现代码引发异常。 （有关详细信息，请参阅 [.NET Native 和编译](../../../docs/framework/net-native/net-native-and-compilation.md)。）若要消除此异常，必须将条目添加至[运行时指令 (rd.xml) 文件](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)，以便 .NET Native 工具链可以使元数据或实现代码在运行时可用。 有两个可用的故障排除程序，将生成要添加到运行时指令文件的必需条目：  
  
    - 类型的 [MissingMetadataException 故障排除程序](https://dotnet.github.io/native/troubleshooter/type.html) 。  
  
    - 方法的 [MissingMetadataException 故障排除程序](https://dotnet.github.io/native/troubleshooter/method.html) 。  
  
     有关详细信息，请参阅[反射和 .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md)。  
  
## <a name="see-also"></a>请参阅

- [将 Windows 应用商店应用迁移到 .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)

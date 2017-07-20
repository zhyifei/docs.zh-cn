---
title: "如何：创建 COM 包装 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM, 包装创建"
  - "COM, 包装 Visual Studio"
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：创建 COM 包装
您可以使用 [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] 功能或 .NET Framework 工具 Tlbimp.exe 和 Regasm.exe 来创建组件对象模型 \(COM\) 包装。  这两种方法都生成两种类型的 COM 包装：  
  
-   一个类型库的 [运行时可调用包装](../../../docs/framework/interop/runtime-callable-wrapper.md)，运行托管代码中的 COM 对象。  
  
-   具有所需注册表设置的 [COM 可调用包装](../../../docs/framework/interop/com-callable-wrapper.md)，运行本机应用程序中的托管对象。  
  
 在 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 中，可以向您的项目中添加 COM 包装作为一个引用。  
  
## 在托管应用程序中包装 COM 对象  
  
#### 若要使用 Visual Studio 创建运行时可调用包装  
  
1.  打开托管应用程序的项目。  
  
2.  在**“项目”**菜单上，单击**“显示所有文件”**。  
  
3.  在**“项目”**菜单上，单击**“添加引用”**。  
  
4.  在“添加引用”对话框中，单击**“COM”**选项卡，选择您要使用的组件，再单击**“确定”**。  
  
     在**“解决方案资源管理器”**中，请注意 COM 组件已添加到项目中的“引用”文件夹。  
  
 您现在可以编写代码以访问 COM 对象。  开始，您可以声明对象，如使用 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 的 `Imports` 语句或 [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)] 的 `Using` 语句。  
  
> [!NOTE]
>  如果您要对 Microsoft Office 组件进行编程，请先从 Microsoft 下载中心安装 [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) \(PIA\)（Microsoft Office 主互操作程序集）。  在步骤 4 中，选择您要使用的 Office 产品可用的最新版本对象库，如**“Microsoft Word 11.0 对象库”**。  [](http://msdn.microsoft.com/zh-cn/c9d2a8b9-69df-4c0b-90ca-4d85bae063c4)  
  
#### 若要使用 .NET Framework 工具创建运行时可调用包装  
  
-   运行 [Tlbimp.exe（类型库导入程序）](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 工具。  
  
 此工具创建一个程序集，其中包含原始类型库中定义的类型的运行时元数据。  
  
## 包装本机应用程序中的托管对象  
  
#### 若要使用 Visual Studio 创建 COM 可调用包装  
  
1.  为您要在本机代码中运行的托管类创建一个类库项目。  此类必须具有默认构造函数。  
  
     验证 AssemblyInfo 文件中有四部分组成的程序集的完整版本号。  在 Windows 注册表中维护版本需要此号码。  有关版本号的更多信息，请参见[程序集版本控制](../../../docs/framework/app-domains/assembly-versioning.md)。  
  
2.  在**“项目”**菜单上，单击**“属性”**。  
  
3.  单击**“编译”**选项卡。  
  
4.  选中**“为 COM 互操作注册”**复选框。  
  
 当您生成项目时，程序集会自动注册 COM 互操作。  如果您在 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 中生成本机应用程序，您可以通过单击**“项目”**菜单上的**“添加引用”**来使用程序集。  
  
#### 若要使用 .NET Framework 工具创建 COM 可调用包装  
  
-   运行 [Regasm.exe（程序集注册工具）](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 工具。  
  
 此工具读取程序集元数据并将必要的项添加到注册表。  因此，COM 客户端可以透明地创建 .NET Framework 类。  您可以使用该程序集，就像它是本机 COM 类一样。  
  
 您可以对位于任何目录中的程序集运行 Regasm.exe，然后运行 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 将其移动到全局程序集缓存中。  移动程序集并不使位置注册表项无效，因为如果没有在其他地方找到程序集，则始终会检查全局程序集缓存。  
  
## 请参阅  
 [运行时可调用包装](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM 可调用包装](../../../docs/framework/interop/com-callable-wrapper.md)
---
title: '配置项目 （F #）'
description: '了解如何使用项目设计器，当您使用 Visual Studio 中的 F # 项目时。'
ms.date: 05/16/2016
ms.openlocfilehash: a6c9539945bbd32748ffca1434c984402bc3f17b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565459"
---
# <a name="configuring-projects-in-visual-studio"></a>在 Visual Studio 中配置项目

> [!NOTE]
本文不是最新的 Visual Studio 最新的。  它将会更新。

本主题包含有关如何使用信息**项目设计器**F # 项目中处理时。 使用 F # 项目不明显不同于使用 Visual Basic 或 C# 项目。 当你使用 F # 时，通常可以作为主引用使用常规的 Visual Studio 项目文档。 本主题提供有关与其他 Visual Studio 语言，共享的设置的 Visual Studio 文档中的相关信息的链接，并还描述了特定于 F # 设置。

## <a name="project-designer"></a>项目设计器
**项目设计器**的一般用法主题中描述了完全[项目设计器简介](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7)Visual Studio 文档中。 **项目设计器**包含按相关功能分组的多个页面。 适用于 F # 项目的页是主要适用于其他语言的子集。 以下表所述在 F # 中支持的页。 将不可用的页面与的功能不可用在 F # 中，或者可以仅通过更改命令行选项。 在 F # 中可用的页面与 C# 页非常相似，因此链接提供了相关的 C#**项目设计器**页。

|项目设计器页|相关的链接|描述|
|---------------------|-------------|-----------|
|`Application`|[应用程序页，项目设计器&#40;C&#35;&#41;](https://msdn.microsoft.com/library/ms247046.aspx)|使您能够指定应用程序级设置和属性，例如，你创建的库或可执行文件、 应用程序的目标.NET Framework 的版本，和有关其中资源文件的信息的应用程序使用存储。|
|`Build`|[生成页、 项目设计器&#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|使用此选项可控制如何编译的代码。|
|`Build Events`|[生成事件页、 项目设计器&#40;C&#35;&#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|使用此选项可指定命令运行之前或之后编译。|
|`Debug`|[“项目设计器”->“调试”页](https://msdn.microsoft.com/library/2wcdezs5.aspx)|使用此选项可控制应用程序在调试期间的运行方式。 这包括什么使用与你的应用程序的开始目录是什么，命令行和任何特殊调试你想要启用，如本机代码和 SQL 的模式。|
|`Reference Paths`|[管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)|使用此选项可指定要从中搜索程序集的代码，取决于。|

## <a name="f-specific-settings"></a>F # 的特定设置
下表总结了特定于 F # 的设置：

|项目设计器页|设置|描述|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|如果选择，启用对尾部 Microsoft 中间语言 (MSIL) 指令的使用。 这将导致要重用为尾递归函数的堆栈帧。 等效于`--tailcalls`编译器选项。|
|`Build`|`Other flags`|使用此选项可以指定其他编译器命令行选项。|

## <a name="see-also"></a>请参阅
 [要开始使用 Visual Studio 中的 F #](../get-started/get-started-visual-studio.md)  
 [编译器选项](../language-reference/compiler-options.md)  
 [项目设计器简介](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))

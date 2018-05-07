---
title: 诊断符号存储区接口
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="diagnostics-symbol-store-interfaces"></a>诊断符号存储区接口
本主题介绍使编译器生成符号信息以供由调试器使用的非托管的接口。  
  
## <a name="in-this-section"></a>本节内容  
 [IBindingDisplay 接口](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 提供用于显示当前运行的应用程序有关的绑定信息的方法。  
  
 [IDebugAutoAttach 接口](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 定义服务器调用调试器自动附加的接口。  
  
 [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 声明用于注册和注销连接通知源的方法。  
  
 [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 声明用于接收器通知方法。  
  
 [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 声明用于设置通知筛选器的方法。  
  
 [ISymENCUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 提供的编辑并继续功能的信息。  
  
 [ISymUnmanagedAsyncMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 此接口是对读取补充[ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)。  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 允许定义的每个方法符号的可选的异步方法信息。 必须使用打开的方法 (即，对的调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)和[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md))。  
  
 [ISymUnmanagedBinder 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 表示非托管代码的符号联编程序。  
  
 [ISymUnmanagedBinder2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。  
  
 [ISymUnmanagedBinder3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。  
  
 [ISymUnmanagedConstant 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 提供对非托管常量的访问。  
  
 [ISymUnmanagedDispose 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 释放非托管资源。  
  
 [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 表示由符号存储引用的文档。  
  
 [ISymUnmanagedDocumentWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 提供用于写入到符号存储区引用的文档的方法。  
  
 [ISymUnmanagedENCUpdate 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 提供的编辑并继续功能的方法。  
  
 [ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 表示符号存储区内的方法。  
  
 [ISymUnmanagedNamespace 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 表示一个命名空间。  
  
 [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 表示提供对文档、 方法和符号存储区内的变量的访问的符号读取器。  
  
 [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 获取给定方法标记和编辑复制版本号的符号读取器方法。  
  
 [ISymUnmanagedReaderSymbolSearchInfo 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 提供用于获取符号搜索信息的方法。  
  
 [ISymUnmanagedScope 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 表示的方法内的词法范围。  
  
 [ISymUnmanagedScope2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 表示的方法内的词法范围并扩展`ISymUnmanagedScope`接口使用的方法来在范围内获取有关定义的常量的信息...  
  
 [ISymUnmanagedSourceServerModule 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 模块提供源服务器数据。  
  
 [ISymUnmanagedSymbolSearchInfo 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 提供一些方法，获取有关的搜索路径的信息。  
  
 [ISymUnmanagedVariable 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 表示一个变量，例如参数、 本地变量或字段。  
  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。  
  
 [ISymUnmanagedWriter2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。 扩展`ISymUnmanagedWriter`接口。  
  
 [ISymUnmanagedWriter3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 表示符号编写器，并提供方法来定义文档、 序列点、 词法作用域和变量。 扩展`ISymUnmanagedWriter`接口。  
  
 [ISymUnmanagedWriter4 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4 接口。  
  
 [ISymUnmanagedWriter5 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5 接口。  
  
## <a name="related-sections"></a>相关章节  
 [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [诊断符号存储区结构](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)

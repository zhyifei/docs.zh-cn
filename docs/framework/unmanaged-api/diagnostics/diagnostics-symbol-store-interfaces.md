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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787889"
---
# <a name="diagnostics-symbol-store-interfaces"></a>诊断符号存储区接口
本主题介绍启用编译器以生成由调试器使用的符号信息的非托管的接口。  
  
## <a name="in-this-section"></a>本节内容  
 [IBindingDisplay 接口](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 提供显示当前运行的应用程序有关的绑定信息的方法。  
  
 [IDebugAutoAttach 接口](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 服务器调用调试器自动连接定义的接口。  
  
 [INotifyConnection2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 声明用于注册和注销连接通知源的方法。  
  
 [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 声明用于接收器通知的方法。  
  
 [INotifySource2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 声明设置通知筛选器的方法。  
  
 [ISymENCUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 提供有关编辑并继续功能的信息。  
  
 [ISymUnmanagedAsyncMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 此接口是对的阅读补充[ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)。  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 允许定义每个方法符号的可选的异步方法信息。 必须使用与打开方法 (即，调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)并[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md))。  
  
 [ISymUnmanagedBinder 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 表示非托管代码的符号联编程序。  
  
 [ISymUnmanagedBinder2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。  
  
 [ISymUnmanagedBinder3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 表示非托管代码的符号联编程序和扩展`ISymUnmanagedBinder`接口。  
  
 [ISymUnmanagedConstant 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 提供对非托管的常量的访问。  
  
 [ISymUnmanagedDispose 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 释放非托管资源。  
  
 [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 表示由符号存储引用的文档。  
  
 [ISymUnmanagedDocumentWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 提供用于写入到符号存储区引用的文档的方法。  
  
 [ISymUnmanagedENCUpdate 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 提供有关编辑并继续功能的方法。  
  
 [ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 表示符号存储区中的一个方法。  
  
 [ISymUnmanagedNamespace 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 表示一个命名空间。  
  
 [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 表示提供对文档、 方法和符号存储区中的变量的访问的符号读取器。  
  
 [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 获取给定方法标记和编辑复制版本号的符号读取器方法。  
  
 [ISymUnmanagedReaderSymbolSearchInfo 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 提供用于获取符号搜索信息的方法。  
  
 [ISymUnmanagedScope 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 表示一种方法内的词法范围。  
  
 [ISymUnmanagedScope2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 表示在方法中，词法范围并扩展`ISymUnmanagedScope`接口使用的范围内获取有关定义的常量的信息的方法...  
  
 [ISymUnmanagedSourceServerModule 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 提供源服务器数据的模块。  
  
 [ISymUnmanagedSymbolSearchInfo 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 提供了获取有关搜索路径的信息的方法。  
  
 [ISymUnmanagedVariable 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 表示一个变量，例如参数、 局部变量或字段。  
  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。  
  
 [ISymUnmanagedWriter2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。 扩展了`ISymUnmanagedWriter`接口。  
  
 [ISymUnmanagedWriter3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 表示符号编写器，并提供方法用于定义文档、 序列点、 词法作用域和变量。 扩展了`ISymUnmanagedWriter`接口。  
  
 [ISymUnmanagedWriter4 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4 接口。  
  
 [ISymUnmanagedWriter5 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5 接口。  
  
## <a name="related-sections"></a>相关章节  
 [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [诊断符号存储区结构](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)

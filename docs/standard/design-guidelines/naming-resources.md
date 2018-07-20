---
title: 命名资源
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cfda4e6a340d040de02903b9b64f0339751c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="naming-resources"></a>命名资源
由于可以通过某些对象引用可本地化资源，就好像它们是属性一样，因此资源的命名准则与属性准则类似。
  
 **✓ 要**对资源键使用 PascalCasing 。  
  
 **✓ 要**提供描述性的名称而不是短的标识符。  
  
 **X 不要**使用主要 CLR 语言中的语言特定关键字。  
  
 **✓ 要**仅在命名资源中使用字母数字字符和下划线。  
  
 **✓ 要**对异常消息资源使用以下命名约定。
  
 资源标识符应该是异常类型名称加上异常的短标识符：
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)

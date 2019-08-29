---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964380"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
在编译期间取消显示版权标志和信息性消息。  
  
## <a name="syntax"></a>语法  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>备注  
 如果指定`-nologo`, 则编译器不显示版权横幅。 默认情况，`-nologo` 是无效的。  
  
> [!NOTE]
> 此`-nologo`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 以下代码将进行`T2.vb`编译, 并且不显示版权横幅。  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

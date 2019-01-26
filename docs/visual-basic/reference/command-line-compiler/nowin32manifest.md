---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: d0a51b2af8b1d8fcf9f0df8dae457a0d3b570a1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744721"
---
# <a name="-nowin32manifest-visual-basic"></a>-nowin32manifest (Visual Basic)
指示编译器不在可执行文件中嵌入任何应用程序清单。  
  
## <a name="syntax"></a>语法  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a>备注  
 使用此选项时，除非在 Win32 资源文件或以后的生成步骤中提供应用程序清单，否则应用程序会受到 Windows Vista 上虚拟化的影响。 有关虚拟化的详细信息，请参阅 [Windows Vista 上的 ClickOnce 部署](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。  
  
 有关清单创建的详细信息，请参阅 [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)。  
  
## <a name="see-also"></a>请参阅
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)

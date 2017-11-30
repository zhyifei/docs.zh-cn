---
title: /nowin32manifest (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce8e963e88a8080424435caea8b15ba288ae9c28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="nowin32manifest-visual-basic"></a>/nowin32manifest (Visual Basic)
指示编译器不在可执行文件中嵌入任何应用程序清单。  
  
## <a name="syntax"></a>语法  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a>备注  
 使用此选项时，除非在 Win32 资源文件或以后的生成步骤中提供应用程序清单，否则应用程序会受到 Windows Vista 上虚拟化的影响。 有关虚拟化的详细信息，请参阅[ClickOnce 部署在 Windows Vista 上](/visualstudio/deployment/clickonce-deployment-on-windows-vista)。  
  
 有关创建清单的详细信息，请参阅[/win32manifest (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/win32manifest.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [“项目设计器”->“应用程序”页 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)

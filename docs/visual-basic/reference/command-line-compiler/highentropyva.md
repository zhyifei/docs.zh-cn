---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 7934dcaada4675bf687624bef5ed1ea25e842832
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344242"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva （Visual Basic）
指示64位可执行文件或由[-platform： anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项标记的可执行文件是否支持高熵地址空间布局随机化（ASLR）。  
  
## <a name="syntax"></a>语法  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>参数  
 `+` &#124; `-`  
 可选。 默认情况下，或指定 `-highentropyva-`时，此选项处于关闭状态。 如果指定 `-highentropyva` 或 `-highentropyva+`，则选项为 on。  
  
## <a name="remarks"></a>备注  
 如果指定此选项，则当内核将进程的地址空间布局作为 ASLR 的一部分随机化时，Windows 内核的兼容版本可以使用更高的平均信息量。 如果内核使用的平均信息量较高，则可以向内存区域（例如堆栈和堆）分配更多的地址。 因此，猜测特定内存区域的位置会更加困难。  
  
 当选项为 on 时，目标可执行文件及其依赖的任何模块在这些模块作为64位进程运行时，必须能够处理大于 4 gb 的指针值。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

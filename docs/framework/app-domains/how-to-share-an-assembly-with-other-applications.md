---
title: 如何：与其他应用程序共享程序集
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b4c183c3fc0b04121be8bbc2db4027887cbc3132
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644295"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a>如何：与其他应用程序共享程序集
程序集可以是私有或共享程序集：默认情况下，大多数简单程序都包含一个私有程序集，因为它们并不打算由其他应用程序使用。  

若要与其他应用程序共享程序集，则必须将它放置在[全局程序集缓存 (GAC)](gac.md) 中。  
  
共享程序集：
  
1. 创建程序集。 有关详细信息，请参阅[创建程序集](../../standard/assembly/create.md)。  
  
2. 向程序集分配强名称。 有关详细信息，请参阅[如何：使用强名称为程序集签名](../../standard/assembly/sign-strong-name.md)。  
  
3. 将版本信息分配给程序集。 有关详细信息，请参阅[程序集版本控制](../../standard/assembly/versioning.md)。  
  
4. 将程序集添加到全局程序集缓存中。 有关详细信息，请参阅[如何：将程序集安装到全局程序集缓存](install-assembly-into-gac.md)。  
  
5. 从其他应用程序访问该程序集中包含的类型。 有关详细信息，请参阅[如何：引用具有强名称的程序集](../../standard/assembly/reference-strong-named.md)。  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../api/index.md)
- [编程概念 (Visual Basic)](../../../api/index.md)
- [使用程序集编程](../../standard/assembly/index.md)

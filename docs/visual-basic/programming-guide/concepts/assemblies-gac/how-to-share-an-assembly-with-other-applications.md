---
title: 如何： 与其他应用程序 (Visual Basic) 共享程序集
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: a7f6b49e8389108528c44d7464a2e68149dfa940
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44062892"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a>如何： 与其他应用程序 (Visual Basic) 共享程序集
程序集可以是私有或共享程序集：默认情况下，大多数简单程序都包含一个私有程序集，因为它们并不打算由其他应用程序使用。  
  
 若要与其他应用程序共享程序集，必须将它放置在[全局程序集缓存](../../../../framework/app-domains/gac.md) (GAC) 中。  
  
### <a name="sharing-an-assembly"></a>共享程序集  
  
1.  创建程序集。 有关详细信息，请参阅[创建程序集](../../../../framework/app-domains/create-assemblies.md)。  
  
2.  向程序集分配强名称。 有关详细信息，请参阅[如何：使用强名称为程序集签名](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。  
  
3.  将版本信息分配给程序集。 有关详细信息，请参阅[程序集版本控制](../../../../framework/app-domains/assembly-versioning.md)。  
  
4.  将程序集添加到全局程序集缓存中。 有关详细信息，请参阅[如何：将程序集安装到全局程序集缓存](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)。  
  
5.  从其他应用程序访问该程序集中包含的类型。 有关详细信息，请参阅[如何：引用具有强名称的程序集](https://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813)。  
  
## <a name="see-also"></a>请参阅  
 [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)[程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [使用程序集编程](../../../../framework/app-domains/programming-with-assemblies.md)

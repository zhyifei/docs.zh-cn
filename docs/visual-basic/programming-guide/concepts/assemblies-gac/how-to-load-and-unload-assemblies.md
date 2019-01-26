---
title: 如何：加载和卸载程序集 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
ms.openlocfilehash: adfe23c2c70b1f49e23fb7c3866c8dac5c9c09ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549699"
---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a>如何：加载和卸载程序集 (Visual Basic)
在生成时自动加载程序所引用的程序集，但也可以在运行时将特定的程序集加载到当前的应用程序域。 有关详细信息，请参阅[如何：将程序集加载到应用程序域](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。  
  
 在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。 即使程序集不在范围之内，在卸载包含它的所有应用程序域之前，实际的程序集文件都将保持加载状态。  
  
 如果想要卸载某些程序集而不是其他程序集，请考虑创建一个新的应用程序域，在此域中执行代码，然后卸载此应用程序域。 有关详细信息，请参阅[如何：卸载应用程序域](../../../../framework/app-domains/how-to-unload-an-application-domain.md)。  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a>将程序集加载到应用程序域中  
  
1.  使用 <xref:System.AppDomain> 和 <xref:System.Reflection> 类中包含的几种加载方法中的一种。 有关详细信息，请参阅[如何：将程序集加载到应用程序域](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。  
  
### <a name="to-unload-an-application-domain"></a>卸载应用程序域  
  
1.  在没有卸载所有包含单个程序集的应用程序域之前，无法卸载此程序集。 使用 <xref:System.AppDomain> 中的 `Unload` 方法卸载应用程序域。 有关详细信息，请参阅[如何：卸载应用程序域](../../../../framework/app-domains/how-to-unload-an-application-domain.md)。  
  
## <a name="see-also"></a>请参阅
- [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)
- [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [如何：将程序集加载到应用程序域](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)

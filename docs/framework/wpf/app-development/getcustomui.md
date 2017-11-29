---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a>GetCustomUI
如果实现由 PresentationHost.exe 若要从主机中获取自定义的进度和错误消息调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>参数  
 `pwzProgressAssemblyName`  
  
 [out]指向包含主机提供进度用户界面的程序集的指针。  
  
 `pwzProgressClassName`  
  
 [out]最好是主机提供进度用户界面，类的名称[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]文件<xref:System.Windows.Controls.Page>是其顶级元素。 此类驻留在由指定的程序集`pwzProgressAssemblyName`。  
  
 `pwzErrorAssemblyName`  
  
 [out]指向包含主机提供的错误用户界面的程序集的指针。  
  
 `pwzErrorClassName`  
  
 [out]为主机提供的错误的用户类的名称最好接口的 XAML 文件<xref:System.Windows.Controls.Page>是其顶级元素。 此类驻留在由指定的程序集`pwzErrorAssemblyName`。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 HRESULT： 忽略。  
  
## <a name="remarks"></a>备注  
 主机应用程序可能具有 PresentationHost.exe 的默认用户界面可能不符合特定主题。 如果出现这种情况，可以实现主机应用程序[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)返回进度和错误的用户界面到 PresentationHost.exe。 将始终调用 PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)然后才能使用其默认用户界面。  
  
 一次在 PresentationHost 的初始化过程中调用此函数。  
  
## <a name="see-also"></a>另请参阅  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

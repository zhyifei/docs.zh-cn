---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944077"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache>
向服务或安全标记处理程序集合注册令牌重播缓存。  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<缓存 >  
\<tokenReplayCache>  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|type|派生自<xref:System.IdentityModel.Tokens.TokenReplayCache>类的类型。 有关如何指定自定义`type`的详细信息, 请参阅 [自定义类型引用]。
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<caches>](caches.md)|注册服务使用的缓存或安全标记处理程序集合。|  
  
## <a name="remarks"></a>备注  
 令牌重播缓存用于检测重播的标记。 令牌重播检测由[ \<tokenReplayDetection >](tokenreplaydetection.md)元素启用, 该元素还指定了令牌的最长到期时间。  
  
## <a name="example"></a>示例  
 下面的 XML 演示了用于检测重播令牌的自定义缓存配置。  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)

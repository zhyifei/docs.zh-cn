---
title: 여러 IIS 사이트 바인딩 지원
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: e364be55687323d3059c4a7e084818e3f7d54d5f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743439"
---
# <a name="supporting-multiple-iis-site-bindings"></a>여러 IIS 사이트 바인딩 지원
当在 Internet Information Services （IIS）7.0 下承载 Windows Communication Foundation （WCF）服务时，您可能需要提供在同一站点上使用同一协议的多个基址。 이렇게 하면 동일한 서비스에서 여러 다른 URI에 응답할 수 있습니다. 这是有用的当你想要承载的服务在其侦听时 `http://www.contoso.com` 和 `http://contoso.com` 。 내부 사용자에 대한 기본 주소와 외부 사용자에 대한 별도의 기본 주소가 있는 서비스를 만들려는 경우에 유용합니다. 例如：`http://internal.contoso.com` 和 `http://www.contoso.com` 。  
  
> [!NOTE]
> 이 기능은 HTTP 프로토콜을 통해서만 사용할 수 있습니다.  
  
## <a name="multiple-base-addresses"></a>여러 기본 주소  
 此功能仅适用于在 IIS 下承载的 WCF 服务。 이 기능은 기본적으로 사용하지 않도록 설정되어 있습니다. 若要启用它，必须将 `multipleSiteBindingsEnabled` 特性添加到 web.config 文件中的 <`serviceHostingEnvironment`> 元素，并将其设置为 `true`，如下面的示例中所示。  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 当在 IIS 下承载 WCF 服务时，IIS 基于包含该应用程序的虚拟目录的 URI 为你创建一个基址。 인터넷 정보 서비스 관리자를 사용하여 웹 사이트에 하나 이상의 바인딩을 추가하여 동일한 프로토콜을 사용하는 기본 주소를 추가할 수 있습니다. 각 바인딩에 대해 프로토콜(HTTP 또는 HTTPS), IP 주소, 포트 및 호스트 이름을 지정합니다. 有关使用 Internet Information Services 管理器的详细信息，请参阅[Iis 管理器（iis 7）](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753842(v=ws.10))。 有关将绑定添加到网站的详细信息，请参阅[创建网站（IIS 7）](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772350(v=ws.10))  
  
 为同一站点指定多个基址会影响 WCF 帮助页的内容、导入架构和服务生成的 WSDL/MEX 信息。 WCF 帮助页显示用于生成可与服务进行通信的 WCF 客户端的命令行。 이 명령줄에는 웹 사이트에 대한 IIS 바인딩에 지정된 첫 번째 주소만 포함됩니다. 마찬가지로 스키마를 가져올 때도 IIS 바인딩에 지정된 첫 번째 기본 주소만 사용됩니다. WSDL 및 MEX 데이터에는 IIS 바인딩에 지정된 모든 기본 주소가 포함됩니다.  
  
> [!WARNING]
> 이는 서비스에 두 개의 기본 주소가 있으면 하나는 내부 사용자용이고 다른 하나는 외부 사용자용이며, 두 주소 모두 서비스에서 생성되는 WSDL/MEX 정보에 지정됨을 의미합니다.

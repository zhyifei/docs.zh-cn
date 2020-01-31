---
title: 安全策略和工程
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: 57ee0c8242c0bca1b2c76e7751ed25f6a889c264
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741845"
---
# <a name="wpf-security-strategy---security-engineering"></a>WPF 보안 전략 - 보안 엔지니어링
신뢰할 수 있는 컴퓨팅은 보안 코드 생성을 보장하기 위한 Microsoft 이니셔티브입니다. 可信计算计划的关键要素是 Microsoft 安全开发生命周期 (SDL)。 SDL 是一种工程实践，与标准工程流程结合使用，以促进安全代码的交付。 SDL 包含10个阶段，其中包含规范化结合、可度量性和其他结构的最佳实践，其中包括：  
  
- 보안 디자인 분석  
  
- 도구 기반 품질 검사  
  
- 침투 테스트  
  
- 최종 보안 검토  
  
- 릴리스 후 제품 보안 관리  
  
## <a name="wpf-specifics"></a>WPF 고유 정보  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 工程团队都适用并扩展 SDL，其中包括以下重要方面：  
  
 [위협 모델링](#threat_modeling)  
  
 [보안 분석 및 편집 도구](#tools)  
  
 [테스트 기술](#techniques)  
  
 [중요한 코드 관리](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a>위협 모델링  
 威胁建模是 SDL 的核心组件，用于分析系统，以确定潜在的安全漏洞。 취약상이 식별되면 위협 모델링은 적절한 완화가 적용되었는지도 확인합니다.  
  
 높은 수준에서 위협 모델링은 식품점을 예로 들어 다음과 같은 주요 단계를 포함합니다.  
  
1. **자산 식별** 식품점의 자산에는 직원, 금고, 현금 등록기 및 재고가 포함될 수 있습니다.  
  
2. **진입점 열거** 식품점의 진입점에는 앞문과 뒷문, 창, 하역장 및 에어컨 장치가 포함될 수 있습니다.  
  
3. **진입점을 통한 자산 공격 조사** 한 가지 가능한 공격은 *에어컨* 진입점을 통해 식품점의 *금고* 자산을 대상으로 할 수 있습니다. 에어컨 장치의 나사를 풀어 금고를 상점 외부로 끌고 나갈 수 있습니다.  
  
 위협 모델링은 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 전체에 적용되며 다음을 포함합니다.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파서가 파일을 읽고, 텍스트를 해당 개체 모델 클래스에 매핑하고, 실제 코드를 만드는 방법  
  
- 창 핸들(hWnd)이 만들어지고, 메시지를 보내고, 창의 내용을 렌더링하는 데 사용되는 방법  
  
- 데이터 바인딩이 리소스를 가져오고 시스템과 상호 작용하는 방법  
  
 이러한 위협 모델은 개발 프로세스 중 보안 디자인 요구 사항과 위협 완화를 식별하는 데 중요합니다.  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a>소스 분석 및 편집 도구  
 除了 SDL 的手动安全代码评审元素外，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 团队还使用几个工具进行源分析和关联编辑，以减少安全漏洞。 다음을 포함하여 다양한 소스 도구가 사용됩니다.  
  
- **FXCop**: 상속 규칙에서 코드 액세스 보안 사용 및 비관리 코드와 안전하게 상호 운용하는 방법에 이르기까지 관리 코드에서 일반적인 보안 문제를 찾습니다. [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29)을 참조하세요.  
  
- **Prefix/Prefast**: 비관리 코드에서 버퍼 오버런, 형식 문자열 문제 및 오류 검사와 같은 보안 취약성 및 일반적인 보안 문제를 찾습니다.  
  
- **금지된 API**: 소스 코드를 검색하여 `strcpy`와 같이 보안 문제가 발생하는 것으로 잘 알려진 함수가 실수로 사용되었는지 식별합니다. 一旦确定，这些函数将被替换为更安全的替代项。  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a>테스트 기술  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]는 다음을 포함하는 다양한 보안 테스트 기술을 사용합니다.  
  
- **白盒测试**：测试人员查看源代码，然后构建利用测试。
  
- **Blackbox 테스트**: 테스터가 API 및 기능을 검사하여 보안 익스플로이트를 찾은 다음 제품을 공격하려고 합니다.  
  
- **다른 제품의 보안 문제 재발**: 해당하는 경우 관련 제품의 보안 문제를 테스트합니다. 例如，已识别 Internet Explorer 的大约60安全问题的适当变体，并尝试将其适用性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]。  
  
- **파일 퍼지 테스트를 통한 도구 기반 침투 테스트**: 파일 퍼지 테스트는 다양한 입력을 통해 파일 판독기의 입력 범위를 악용합니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에서 이 기술이 사용되는 한 가지 예는 이미지 디코딩 코드 오류 검사입니다.  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a>중요한 코드 관리  
 对于 XAML 浏览器应用程序（Xbap），[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 通过使用 .NET Framework 支持来标记和跟踪可提升特权的安全关键代码来生成安全沙盒（请参阅[WPF 安全策略-平台安全性](wpf-security-strategy-platform-security.md)中的**安全关键方法**）。 보안에 중요한 코드의 높은 보안 품질 요구 사항을 감안하여 이러한 코드는 추가 수준의 소스 관리 제어 및 보안 감사를 받습니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 약 5%-10%는 전담 검토팀이 검토하는 보안에 중요한 코드로 구성됩니다. 소스 코드 및 체크 인 프로세스는 보안에 중요한 코드를 추적하고 중요한 엔터티(예: 중요한 코드가 포함된 메서드)를 사인오프 상태로 매핑하여 관리합니다. 사인오프 상태에는 하나 이상의 검토자 이름이 포함됩니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 각 일별 빌드는 중요한 코드를 이전 빌드의 코드와 비교하여 승인되지 않은 변경 내용을 확인합니다. 엔지니어가 검토팀의 승인 없이 중요한 코드를 수정하는 경우 식별되어 즉시 수정됩니다. 이 프로세스를 통해 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 샌드박스 코드에 특히 높은 수준의 감시를 적용하고 유지할 수 있습니다.  
  
## <a name="see-also"></a>另请参阅

- [Security](security-wpf.md)
- [WPF 부분 신뢰 보안](wpf-partial-trust-security.md)
- [WPF 보안 전략 - 플랫폼 보안](wpf-security-strategy-platform-security.md)
- [可信计算](https://www.microsoft.com/mscorp/twc/default.mspx)
- [.NET의 보안](../../standard/security/index.md)

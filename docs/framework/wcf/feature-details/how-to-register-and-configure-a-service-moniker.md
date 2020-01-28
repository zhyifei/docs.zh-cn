---
title: '방법: 서비스 모니커 등록 및 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: fc0b2d00bcc8e3b14c491446f16297c1036b783b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747090"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>방법: 서비스 모니커 등록 및 구성

在使用具有类型协定的 COM 应用程序中使用 Windows Communication Foundation （WCF）服务名字对象之前，必须使用 COM 注册所需的属性化类型，并使用所需的绑定配置 COM 应用程序和名字对象configuration.

## <a name="register-the-required-attributed-types-with-com"></a>向 COM 注册所需的属性化类型

1. 使用 "工作的[元数据实用工具（svcutil.exe）](../servicemodel-metadata-utility-tool-svcutil-exe.md) " 工具从 WCF 服务中检索元数据协定。 这会生成 WCF 客户端程序集和客户端应用程序配置文件的源代码。

2. 어셈블리의 형식이 `ComVisible`로 표시되는지 확인합니다. 为此，请将以下属性添加到 Visual Studio 项目中的*AssemblyInfo.cs*文件。

    ```csharp
    [assembly: ComVisible(true)]
    ```

3. 将托管 WCF 客户端编译为具有强名称的程序集。 이렇게 하려면 암호화된 키 쌍으로 서명해야 합니다. 자세한 내용은 [강력한 이름으로 어셈블리 서명](../../../standard/assembly/sign-strong-name.md)을 참조하세요.

4. 어셈블리 등록(Regasm.exe) 도구에 `-tlb` 옵션을 사용하여 어셈블리의 형식을 COM에 등록합니다.

5. 전역 어셈블리 캐시(Gacutil.exe) 도구를 사용하여 어셈블리를 전역 어셈블리 캐시에 추가합니다.

    > [!NOTE]
    > 어셈블리에 서명하고 전역 어셈블리 캐시에 추가하는 것은 선택적 단계이지만 런타임에 올바른 위치에서 어셈블리를 로드하는 프로세스를 단순화할 수 있습니다.

## <a name="configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>用所需的绑定配置配置 COM 应用程序和名字对象

- 在客户端应用程序的配置文件中，将配置文件（在生成的客户端应用程序配置文件中）生成（由配置的[元数据实用工具（svcutil.exe）](../servicemodel-metadata-utility-tool-svcutil-exe.md)生成）。 예를 들어 이름이 CallCenterClient.exe인 Visual Basic 6.0 실행 파일에 대해 실행 파일과 동일한 디렉터리 내의 CallCenterConfig.exe.config 파일에 구성을 저장해야 합니다. 이제 클라이언트 애플리케이션에서 모니커를 사용할 수 있습니다. 请注意，如果使用 WCF 提供的标准绑定类型之一，则不需要绑定配置。

     다음 형식이 등록됩니다.

    ```csharp
    using System.ServiceModel;

    [ServiceContract]
    public interface IMathService
    {
        [OperationContract]
        public int Add(int x, int y);
        [OperationContract]
        public int Subtract(int x, int y);
    }
    ```

     애플리케이션은 `wsHttpBinding` 바인딩을 사용하여 노출됩니다. 지정된 형식과 애플리케이션 구성에 대해 다음 예제 모니커 문자열이 사용됩니다.

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1
    ```

     또는

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}
    ```

     다음 샘플 코드와 같이 `IMathService` 형식을 포함하는 어셈블리에 대한 참조를 추가한 후 Visual Basic 6.0 애플리케이션 내에서 이러한 모니커 문자열 중 하나를 사용할 수 있습니다.

    ```vb
    Dim mathProxy As IMathService
    Dim result As Integer

    Set mathProxy = GetObject( _
            "service4:address=http://localhost/MathService, _
            binding=wsHttpBinding, _
            bindingConfiguration=Binding1")

    result = mathProxy.Add(3, 5)
    ```

     在此示例中，绑定配置 `Binding1` 的定义存储在客户端应用程序的适当命名的配置文件中，如*vb6appname*。

    > [!NOTE]
    > C#, C++ 또는 다른 모든 .NET 언어 애플리케이션으로 유사한 코드를 사용할 수 있습니다.

    > [!NOTE]
    > 如果名字对象格式不正确，或者服务不可用，则对 `GetObject` 的调用将返回错误 "语法无效"。 이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.

     尽管本主题重点介绍如何将服务名字对象用于 Visual Basic 6.0 代码，但你可以使用其他语言的服务名字对象。 C++ 코드에서 모니커를 사용하는 경우 다음 코드와 같이 "no_namespace named_guids raw_interfaces_only"를 사용하여 Svcutil.exe에서 생성된 어셈블리를  가져와야 합니다.

    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids
    ```

     모든 메서드에서 `HResult`를 반환하도록 가져온 인터페이스 정의를 수정합니다. 다른 모든 반환 값은 출력 매개 변수로 변환됩니다. 전체 메서드 실행은 동일하게 유지됩니다. 이 경우 프록시에서 메서드를 호출할 때 예외의 원인을 확인할 수 있습니다. 이 기능은 C++ 코드에서만 사용할 수 있습니다.

## <a name="see-also"></a>另请参阅

- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)

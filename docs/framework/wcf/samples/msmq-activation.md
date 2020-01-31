---
title: MSMQ 활성화
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 805ab78908b4d1146cce94cac5357bafbb35c832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744788"
---
# <a name="msmq-activation"></a>MSMQ 활성화

이 샘플에서는 메시지 큐에서 읽은 WAS(Windows Process Activation Service)에서 애플리케이션을 호스트하는 방법을 보여 줍니다. 此示例使用 `netMsmqBinding`，并基于[双向通信](../../../../docs/framework/wcf/samples/two-way-communication.md)示例。 이 경우 서비스는 웹 호스팅 애플리케이션이고 클라이언트는 자체 호스트되며 전송된 구매 주문의 상태를 확인하기 위해 콘솔에 출력됩니다.

> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.

> [!NOTE]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> \<InstallDrive>:\WF_WCF_Samples
>
> 如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （WCF）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WCF 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 이 샘플은 다음 디렉터리에 있습니다.
>
> \<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.

Windows 进程激活服务（WAS）是 Windows Server 2008 的新进程激活机制，它提供了类似 IIS 的功能，这些功能以前仅对使用非 HTTP 协议的应用程序可用。 Windows Communication Foundation （WCF）使用侦听器适配器接口传递通过 WCF 支持的非 HTTP 协议（如 TCP、命名管道和 MSMQ）接收的激活请求。 HTTP가 아닌 프로토콜을 통해 요청을 수신하는 기능은 SMSvcHost.exe에서 실행되는 관리되는 Windows 서비스에 의해 호스트됩니다.

Net.Msmq Listener Adapter 서비스(NetMsmqActivator)는 큐의 메시지에 기초하여 큐에 대기 중인 애플리케이션을 활성화합니다.

클라이언트는 트랜잭션의 범위 내에서 서비스에 구매 주문을 보냅니다. 서비스는 트랜잭션의 주문을 수신하고 처리합니다. 그런 다음 서비스는 주문 상태와 함께 클라이언트를 콜백합니다. 양방향 통신을 쉽게 수행하기 위해 클라이언트와 서비스는 둘 다 큐를 사용하여 구매 주문과 주문 상태를 큐에 삽입합니다.

서비스 계약 `IOrderProcessor`는 큐를 사용하는 단방향 서비스 작업을 정의합니다. 이 서비스 작업은 회신 엔드포인트를 사용하여 주문 상태를 클라이언트에게 보냅니다. 회신 엔드포인트의 주소는 주문 상태를 클라이언트에게 다시 보내는 데 사용되는 큐의 URI입니다. 주문 처리 애플리케이션에서 이 계약을 구현합니다.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

주문 상태를 보낼 회신 계약은 클라이언트에 의해 지정됩니다. 클라이언트는 주문 상태 계약을 구현합니다. 서비스는 이 계약의 생성된 클라이언트를 사용하여 주문 상태를 다시 클라이언트에게 보냅니다.

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

서비스 작업은 전송된 구매 주문을 처리합니다. 큐에서 메시지를 수신하는 데 사용되는 트랜잭션의 자동 인리스트먼트 및 서비스 작업 완료 시의 트랜잭션의 자동 완료를 지정하기 위해 <xref:System.ServiceModel.OperationBehaviorAttribute>가 서비스 작업에 적용됩니다. `Orders` 클래스는 주문 처리 기능을 캡슐화합니다. 이 경우에는 구매 주문을 사전에 추가합니다. 서비스 작업이 참여하는 트랜잭션은 `Orders` 클래스의 작업에서 사용할 수 있습니다.

전송된 구매 주문을 처리하는 것 외에도 서비스 작업은 주문 상태에 대해 클라이언트에 의존합니다.

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

사용할 클라이언트 바인딩은 구성 파일을 사용하여 지정됩니다.

MSMQ 큐 이름은 구성 파일의 appSettings 섹션에 지정됩니다. 서비스의 엔드포인트는 구성 파일의 System.serviceModel 섹션에 정의됩니다.

> [!NOTE]
> MSMQ 큐 이름 및 엔드포인트 주소는 약간 다른 주소 지정 규칙을 사용합니다. MSMQ 큐 이름은 로컬 컴퓨터에 점(.)을, 그 경로에는 백슬래시 구분 기호를 사용합니다. WCF 终结点地址指定一个 net.pipe：方案，使用本地计算机的 "localhost"，并在其路径中使用正斜杠。 원격 컴퓨터에서 호스트되는 큐에서 읽으려면 "." 및 "localhost"를 원격 컴퓨터 이름으로 바꿉니다.

클래스 이름을 가진 .svc 파일은 WAS에서 서비스 코드를 호스트하는 데 사용됩니다.

Service.svc 파일 자체는 `OrderProcessorService`를 만들기 위한 지시문을 포함합니다.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

또한 Service.svc 파일은 System.Transactions.dll이 로드되도록 하는 어셈블리 지시문을 포함합니다.

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

클라이언트는 트랜잭션 범위를 만듭니다. 서비스와의 통신이 트랜잭션 범위 내에서 발생하므로 트랜잭션 범위는 모든 메시지가 성공하거나 실패하는 원자 단위로 간주됩니다. 트랜잭션은 트랜잭션 범위에서 `Complete`를 호출하여 커밋합니다.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

    // Create the purchase order
    PurchaseOrder po = new PurchaseOrder();
    po.CustomerId = "somecustomer.com";
    po.PONumber = Guid.NewGuid().ToString();

    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
    lineItem1.ProductId = "Blue Widget";
    lineItem1.Quantity = 54;
    lineItem1.UnitCost = 29.99F;

    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
    lineItem2.ProductId = "Red Widget";
    lineItem2.Quantity = 890;
    lineItem2.UnitCost = 45.89F;

    po.orderLineItems = new PurchaseOrderLineItem[2];
    po.orderLineItems[0] = lineItem1;
    po.orderLineItems[1] = lineItem2;

    //Create a transaction scope.
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

클라이언트 코드는 서비스로부터 주문 상태를 수신하기 위해 `IOrderStatus` 계약을 구현합니다. 이 경우 주문 상태가 출력됩니다.

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

주문 상태 큐는 `Main` 메서드에 생성됩니다. 다음 샘플 구성과 같이 클라이언트 구성에는 주문 상태 서비스를 호스트하는 주문 상태 서비스 구성이 포함됩니다.

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

샘플을 실행하면 클라이언트 및 서비스 동작이 서버 콘솔 창과 클라이언트 콘솔 창에 모두 표시됩니다. 클라이언트에서 서버 수신 메시지를 볼 수 있습니다. 서버와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.

클라이언트는 서버가 보낸 주문 상태 정보를 표시합니다.

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1. 确保安装了 IIS 7.0，因为 WAS 激活所必需的。

2. 确保已对[Windows Communication Foundation 示例执行了一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。 此外，还必须安装 WCF 非 HTTP 激活组件：

    1. **시작** 메뉴에서 **제어판**을 선택합니다.

    2. 选择 "**程序和功能**"。

    3. 单击 **"打开或关闭 Windows 功能"** 。

    4. 在 "**功能摘要**" 下，单击 "**添加功能**"。

    5. 展开**Microsoft .NET Framework 3.0**节点并检查**Windows Communication Foundation 非 HTTP 激活**功能。

3. C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.

4. 명령 창에서 client.exe를 실행하여 클라이언트를 실행합니다. 이렇게 하면 큐가 만들어지고 메시지가 큐에 전송됩니다. 메시지를 읽는 서비스의 결과를 확인하기 위해 클라이언트를 실행된 상태로 둡니다.

5. MSMQ 활성화 서비스는 기본적으로 네트워크 서비스로 실행됩니다. 따라서 애플리케이션을 활성화하는 데 사용되는 큐는 네트워크 서비스에 대한 수신 및 피킹 권한이 있어야 합니다. 다음과 같이 메시지 큐 MMC를 사용하여 이러한 권한을 추가할 수 있습니다.

    1. 从 "**开始**" 菜单中，单击 "**运行**"，然后键入 `Compmgmt.msc` 然后按 enter。

    2. 在 "**服务和应用程序**" 下，展开 "**消息队列**"。

    3. 单击 "**专用队列**"。

    4. 右键单击队列（servicemodelsamples/服务），然后选择 "**属性**"。

    5. 在 "**安全**" 选项卡上，单击 "**添加**" 并向网络服务授予 "查看" 和 "接收" 权限。

6. MSMQ 활성화를 지원하도록 WAS(Windows Process Activation Service)를 구성합니다.

    편의를 위해 다음 단계는 샘플 디렉터리에 있는 AddMsmqSiteBinding.cmd라는 배치 파일에서 구현됩니다.

    1. net.msmq 활성화를 지원하려면 먼저 기본 웹 사이트를 net.msmq 프로토콜에 바인딩해야 합니다. 이 작업은 IIS 7.0 관리 도구 집합과 함께 설치되는 appcmd.exe를 사용하여 수행할 수 있습니다. 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > 이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.

        이 명령은 기본 웹 사이트에 net.msmq 사이트 바인딩을 추가합니다.

    2. 사이트 내의 모든 애플리케이션이 공통된 net.msmq 바인딩을 공유하지만 각 애플리케이션에서 개별적으로 net.msmq 지원을 사용하도록 설정할 수 있습니다. /servicemodelsamples 애플리케이션에서 net.msmq를 사용하도록 설정하려면 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > 이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.

        此命令允许使用 `http://localhost/servicemodelsamples` 和 `net.msmq://localhost/servicemodelsamples`访问/servicemodelsamples 应用程序。

7. 아직 설정하지 않은 경우 MSMQ 활성화 서비스를 사용하도록 설정합니다. 从 "**开始**" 菜单中，单击 "**运行**"，然后键入 `Services.msc`。 在服务列表中搜索**Net.tcp 侦听器适配器**。 右键单击并选择 "**属性**"。 将 "**启动类型**" 设置为 "**自动**"，单击 "**应用**"，然后单击 "**开始**" 按钮。 이 단계는 Net.Msmq Listener Adapter 서비스를 처음 사용하기 전에 한 번만 수행해야 합니다.

8. 若要以单机配置或跨计算机配置来运行示例，请按照[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的说明进行操作。 또한 구매 주문 전송 시에 큐의 URI에서 컴퓨터 이름이 반영되도록 구매 주문을 전송하는 클라이언트에서 코드를 변경합니다. 다음 코드를 사용합니다.

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. 이 샘플에 대해 추가한 net.msmq 사이트 바인딩을 제거합니다.

    편의를 위해 다음 단계는 샘플 디렉터리에 있는 RemoveMsmqSiteBinding.cmd라는 배치 파일에서 구현됩니다.

    1. 권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 사용된 프로토콜 목록에서 net.msmq를 제거합니다.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > 이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.

    2. 권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 net.msmq 사이트 바인딩을 제거합니다.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > 이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.

    > [!WARNING]
    > 배치 파일을 실행하면 DefaultAppPool이 .NET Framework 버전 2.0을 사용하여 실행되도록 다시 설정됩니다.

기본적으로 `netMsmqBinding` 바인딩 전송을 사용하여 보안이 설정됩니다. `MsmqAuthenticationMode` 및 `MsmqProtectionLevel` 속성은 모두 전송 보안의 형식을 결정합니다. 기본적으로 인증 모드는 `Windows`로 설정되고 보호 수준은 `Sign`으로 설정됩니다. MSMQ에서 인증 및 서명 기능을 제공하려면 도메인에 속해 있어야 합니다. 도메인에 속하지 않은 컴퓨터에서 이 샘플을 실행할 경우 "사용자의 내부 메시지 큐 인증서가 없습니다."라는 오류 메시지가 표시됩니다.

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>작업 그룹에 가입된 컴퓨터에서 샘플을 실행하려면

1. 컴퓨터가 도메인의 일부가 아닌 경우 다음 샘플 구성과 같이 인증 모드와 보호 수준을 none으로 설정하여 전송 보안을 해제합니다.

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. 샘플을 실행하기 전에 서버와 클라이언트 모두에서 구성을 변경합니다.

    > [!NOTE]
    > `security mode`를 `None`으로 설정하는 것은 `MsmqAuthenticationMode`, `MsmqProtectionLevel` 및 `Message` 보안을 `None`으로 설정하는 것과 같습니다.

3. 작업 그룹에 가입된 컴퓨터에서 활성화를 사용하려면 활성화 서비스와 작업자 프로세스가 둘 다 특정 사용자 계정(두 경우에 동일해야 함)으로 실행되어야 하고 큐에는 해당 사용자 계정에 대한 ACL이 있어야 합니다.

     작업자 프로세스가 실행될 때 사용되는 ID를 변경하려면

    1. Inetmgr.exe를 실행합니다.

    2. 在 "**应用程序池**" 下，右键单击**AppPool** （通常为**DefaultAppPool**），然后选择 "**设置应用程序池默认值 ...** "。

    3. 특정 사용자 계정을 사용하도록 ID 속성을 변경합니다.

     활성화 서비스가 실행될 때 사용되는 ID를 변경하려면

    1. Services.msc를 실행합니다.

    2. 右键单击**Listener 适配器**，然后选择 "**属性**"。

4. 更改 "**登录**" 选项卡中的帐户。

5. 작업 그룹에서 서비스는 또한 제한되지 않은 토큰을 사용하여 실행되어야 합니다. 이렇게 하려면 명령 창에서 다음을 실행합니다.

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a>另请参阅

- [AppFabric 宿主和持久性示例](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))

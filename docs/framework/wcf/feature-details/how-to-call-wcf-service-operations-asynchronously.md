---
title: "如何：以异步方式调用 WCF 服务操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f8a22a5a5b9f388cdfb7b5e5edfa0a54b628aa0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>如何：以异步方式调用 WCF 服务操作
本主题介绍客户端如何以异步方式访问服务操作。 本主题中的服务可实现 `ICalculator` 接口。 通过使用事件驱动的异步调用模型，客户端可以对此接口异步调用操作。 (有关基于事件的异步调用模型的详细信息，请参阅[使用基于事件的异步模式的多线程编程](http://go.microsoft.com/fwlink/?LinkId=248184))。 有关演示如何实现一个操作以异步方式在服务中的示例，请参阅[如何： 实现异步服务操作](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)。 有关同步和异步操作的详细信息，请参阅[同步和异步操作](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)。  
  
> [!NOTE]
>  使用 <xref:System.ServiceModel.ChannelFactory%601> 时，不支持事件驱动的异步调用模型。 有关进行异步调用使用信息<xref:System.ServiceModel.ChannelFactory%601>，请参阅[如何： 调用操作以异步方式使用通道工厂](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>以异步方式调用 WCF 服务操作  
  
1.  运行[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)两个工具`/async`和`/tcv:Version35`一起命令选项，如下面的命令中所示。  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     除了同步操作和基于委托的标准异步操作之外，此操作还会生成 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端类，其中包含以下内容：  
  
    -   两个 <`operationName` > `Async`用于基于事件的异步调用方法的操作。 例如:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   窗体的操作已完成事件 <`operationName` > `Completed`用于基于事件的异步调用方法。 例如:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType>每个操作的类型 (窗体的 <`operationName`>`CompletedEventArgs`) 用于基于事件的异步调用方法。 例如:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  在调用应用程序中，创建一个要在异步操作完成时调用的回调方法，如下面的示例代码所示。  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  在调用该操作之前, 使用一个新的泛型<xref:System.EventHandler%601?displayProperty=nameWithType>类型的 <`operationName` > `EventArgs`将 （在上一步中创建） 的处理程序方法添加到 <`operationName` > `Completed`事件。 然后调用 <`operationName` > `Async`方法。 例如:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>示例  
  
> [!NOTE]
>  基于事件的异步模型设计准则规定，如果返回了多个值，则一个值会作为 `Result` 属性返回，其他值会作为 <xref:System.EventArgs> 对象上的属性返回。 因此产生的结果之一是，如果客户端使用基于事件的异步命令选项导入元数据，且该操作返回多个值，则默认的 <xref:System.EventArgs> 对象返回一个值作为 `Result` 属性，返回的其余值是 <xref:System.EventArgs> 对象的属性。如果要将消息对象作为 `Result` 属性来接收并要使返回的值作为该对象上的属性，请使用 `/messageContract` 命令选项。 这会生成一个签名，该签名会将响应消息作为 `Result` 对象上的 <xref:System.EventArgs> 属性返回。 然后，所有内部返回值就都是响应消息对象的属性了。  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>请参阅  
 [如何：实现异步服务操作](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)

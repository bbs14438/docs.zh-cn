---
title: "ICorDebugValue::GetType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a79ef332361fdaa3a23cc4e13daa8b4a8303d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType 方法
获取此"ICorDebugValue"对象的基元类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pType`  
 [out]指向"CorElementType"枚举，该值指示的值类型的值的指针。  
  
## <a name="remarks"></a>备注  
 如果对象是复杂的运行时类型，可能通过的适当子类检查该类型`ICorDebugValue`接口。 例如，"ICorDebugObjectValue"，该类继承自`ICorDebugValue`，表示一个复杂类型。  
  
 `GetType`和[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)方法均返回的值类型有关的信息。 它们会取代通过识别泛型[icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
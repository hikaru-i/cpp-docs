---
title: "set_unexpected (CRT)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - set_unexpected
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
apitype: DLLExport
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# set_unexpected (CRT)
Installs your own termination function to be called by `unexpected`.  
  
## Syntax  
  
```  
unexpected_function set_unexpected(  
   unexpected_function unexpFunction   
);  
```  
  
#### Parameters  
 `unexpFunction`  
 Pointer to a function that you write to replace the `unexpected` function.  
  
## Return Value  
 Returns a pointer to the previous termination function registered by `_set_unexpected` so that the previous function can be restored later. If no previous function has been set, the return value may be used to restore the default behavior; this value may be NULL.  
  
## Remarks  
 The `set_unexpected` function installs `unexpFunction` as the function called by `unexpected`. `unexpected` is not used in the current C++ exception-handling implementation. The `unexpected_function` type is defined in EH.H as a pointer to a user-defined unexpected function, `unexpFunction` that returns `void`. Your custom `unexpFunction` function should not return to its caller.  
  
```  
typedef void ( *unexpected_function )( );  
```  
  
 By default, `unexpected` calls `terminate`. You can change this default behavior by writing your own termination function and calling `set_unexpected` with the name of your function as its argument. `unexpected` calls the last function given as an argument to `set_unexpected`.  
  
 Unlike the custom termination function installed by a call to `set_terminate`, an exception can be thrown from within `unexpFunction`.  
  
 In a multithreaded environment, unexpected functions are maintained separately for each thread. Each new thread needs to install its own unexpected function. Thus, each thread is in charge of its own unexpected handling.  
  
 In the current Microsoft implementation of C++ exception handling, `unexpected` calls `terminate` by default and is never called by the exception-handling run-time library. There is no particular advantage to calling `unexpected` rather than `terminate`.  
  
 There is a single `set_unexpected` handler for all dynamically linked DLLs or EXEs; even if you call `set_unexpected` your handler may be replaced by another or that you are replacing a handler set by another DLL or EXE.  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`set_unexpected`|<eh.h>|  
  
 For additional compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md) in the Introduction.  
  
## .NET Framework Equivalent  
 Not applicable. To call the standard C function, use `PInvoke`. For more information, see [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## See Also  
 [Exception Handling Routines](../VS_visualcpp/Exception-Handling-Routines.md)   
 [abort](../VS_visualcpp/abort.md)   
 [_get_unexpected](../VS_visualcpp/_get_unexpected.md)   
 [set_terminate](../VS_visualcpp/set_terminate--CRT-.md)   
 [terminate](../VS_visualcpp/terminate--CRT-.md)   
 [unexpected](../VS_visualcpp/unexpected--CRT-.md)
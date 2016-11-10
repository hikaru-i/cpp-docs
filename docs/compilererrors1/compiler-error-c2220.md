---
title: "Compiler Error C2220"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Compiler Error C2220
warning treated as error - no object file generated  
  
 [/WX](../buildref/-w---w0---w1---w2---w3---w4---w1---w2---w3---w4---wall---wd---we---wo---wv---wx--warning-level-.md) tells the compiler to treat all warnings as errors. Because an error occurred, no object or executable file was generated.  
  
 This error only appears when the **/WX** flag is set and a warning occurs during compilation. To fix this error, you must eliminate every warning in your project.  
  
### To fix, use one of the following techniques  
  
-   Fix the problems that cause warnings in your project.  
  
-   Compile at a lower warning level—for example, use **/W3** instead of **/W4**.  
  
-   Use a [warning](../c/warning.md) pragma to disable or suppress a specific warning.  
  
-   Don't use **/WX** to compile.
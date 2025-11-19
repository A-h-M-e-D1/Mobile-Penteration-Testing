### What is Binder
-  is a Linux kernel driver that is used to transmit the intent from one app to another.
- Provides a secure channel between applications.  
- Uses the RPC (Remote Procedure Call) model >>> 
```This means instead of sending random messages, I can call a function from a different process and use it like a local one.```


-  Binder is used with **AIDL** to define specific methods and parameters, which can then be implemented and exposed through the service.

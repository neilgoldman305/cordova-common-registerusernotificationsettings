
Cordova RegisterUserNotificationSettings Plugin
===============================================

Implements didRegisterUserNotificationSettings and broadcasts the event for listening plugins.

This fork was created to fix a "symbol aready defined" error caused by using two plugins which rely on this dependency.

```obj-c
#import "AppDelegate+APPRegisterUserNotificationSettings.h"

- (void) pluginInitialize
{
    NSNotificationCenter* center = [NSNotificationCenter
                                    defaultCenter];

    [center addObserver:self
               selector:@selector(didRegisterUserNotificationSettings:)
                   name:UIApplicationRegisterUserNotificationSettings
                 object:nil];
}

- (void) didRegisterUserNotificationSettings:(UIUserNotificationSettings*)settings
{
    ...  
}
```
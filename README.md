An Android library which help time out app in both background and foreground.

### Sample

##### Modify your application class or create one if it does not exist and initialize `TimedDog`
##### in your onCreate() method.

```java
class MyApp extends Application{
    
    @Override
    public void onCreate(){
        //...
        TimedDog.init(this);
    }
}
```

##### Extend `TimeoutActivity` in your base activity
```java
class BaseActivity extends TimeoutActivity{
    //...
}
```

##### Finally, start `TimedDog` in your main activity's method. Typically, this is usually the 
##### splash activity.
```java
new TimedDogXWorker.Builder(this)
                .seconds(10)
                .listener(new TimedDogXWorker.OnTimeOutListener() {
            @Override
            public void onTimeOut(boolean isForeground) {

            }
        }).build();
```

#### How To Install

##### Add the jitpack repository to your build.gradle(project level) file
```groovy
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

##### Add the library to your build.gradle(app level) file and rebuild your project
```groovy
implementation 'com.github.devmike01:timeddogx:1.0.0'
```

**That's all**

License
-------

    Copyright 2020 Oladipupo Gbenga

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

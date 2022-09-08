# Driver-Any

## what is driver-any?

Custom step guide library, you can customize the name, description, type, parameters, etc. of the step.

## how do i use

**Import**

Please import it globally first ```import "driver-any/dist/index.css"```

```js
import DriverAny from 'driver-any';

// We first need to create an instance
const driver = new DriverAny({
    pushComponentPosition: "top",
    ifUsePushComponent: true,
    ifClickMaskCloseStep: false,
    animation: true,
    onCloseCallback: () => {console.log("close");},
    onFinishCallback: () => {console.log("finish");},
    onNextCallback: (item) => {console.log("下一步", item);},
    onPrevCallback: (item) => {console.log("上一步", item);},
});

// Next customize each of our steps
driver.configurationSteps([{
    domSelector: "#step1",
    stepDesc: "This is the descriptor for step one",
    customizedPushComponent: "#step1-form",
    pushComponentPosition: "top"
}, {
    domSelector: "#step2",
    stepDesc: "This is the descriptor for step two",
    customizedPushComponent: "#step2-form",
    pushComponentPosition: "right"
}]);

// Finally, start this step to guide
driver.start();
```

## Parameter Description

🤞 Please see types/index.d.ts in the driver-any folder
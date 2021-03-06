---

title: 'Extension Attributes'
weight: 60

menu:
  main:
    identifier: "user-guide-dmn-model-api-extension-elements"
    parent: "user-guide-dmn-model-api"

---


[Custom extensions]({{< relref "reference/dmn11/custom-extensions/index.md" >}}) are a standardized way to extend the DMN model.
The [Camunda extension attrributes]({{< relref "reference/dmn11/custom-extensions/camunda-attributes.md" >}}) are fully implemented in the DMN model API.

Every DMN `Decision` element can have attributes `historyTimeToLive` and `versionTag`.
To access the extension attributes you have to call the `Decision#getCamundaHistoryTimeToLiveString()` and 
`Decision#getVersionTag()` methods. 

```java
String historyTimeToLive = decision.getCamundaHistoryTimeToLiveString();
String versionTag = decision.getVersionTag();
```
To set attributes, use `Decision#setCamundaHistoryTimeToLiveString()` and  `Decision#setVersionTag()`
```java
decision.setCamundaHistoryTimeToLiveString("1000");
decision.setVersionTag("1.0.0");
```

Every `Input` element can have an attribute `inputVariable`. 
This attribute specifies the variable name which can be used to access the result of the input expression in an input entry expression.
It can be set and fetched similarly:

```java
input.setCamundaInputVariable("camundaInput");
input.getCamundaInputVariable();
```

# Poco JSON Parse 

```
using namespace Poco::JSON;
std::string json = "[ {\"test\" : 0}, { \"test1\" : [1, 2, 3], \"test2\" : 4 } ]";
Parser parser;
Var result = parser.parse(json);
Array::Ptr arr = result.extract<Array::Ptr>();
Object::Ptr object = arr->getObject(0); // object == {\"test\" : 0}
int i = object->getElement<int>("test"); // i == 0;
Object::Ptr subObject = *arr->getObject(1); // subObject == {\"test\" : 0}
Array subArr::Ptr = subObject->getArray("test1"); // subArr == [1, 2, 3]
i = result = subArr->get(0); // i == 1;

// copy/convert to Poco::Dynamic::Array
Poco::Dynamic::Array da = *arr;
i = da[0]["test"];     // i == 0
i = da[1]["test1"][1]; // i == 2
i = da[1]["test2"];    // i == 4
```
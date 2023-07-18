# Dart-jsonDecode-and-Encode
import "dart:convert";

void main(){
  
  Map<String, dynamic> dynamicMap={
    "name":"xiao-mei",
    "age":18
  };
  
  //run time type可以輸出後面value存的值的型態，因為原本宣告的是dynamic
  print (dynamicMap["name"].runtimeType);
  print(dynamicMap["age"].runtimeType);
  
  String jsonObjectString = """{"name":"小明", "age":"28"}""";
  
  //用jsonDecode將外部資料型態 轉換成Map形式儲存
  Map<String, dynamic> fromJsonObjectStrToDartMap = jsonDecode(jsonObjectString);
  print (fromJsonObjectStrToDartMap["name"]);
  print (fromJsonObjectStrToDartMap["age"]);
  
  //可以把東西存回map之後 再使用jsonEncode可以存成合法的json型態
  fromJsonObjectStrToDartMap["sex"]="male";
  jsonObjectString= jsonEncode(fromJsonObjectStrToDartMap);
  print (jsonObjectString);
}

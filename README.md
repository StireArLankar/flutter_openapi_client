# flutter_openapi_client

A new Flutter project with codegen swagger.  
Essential files in **my_api** folder:

- **petstore.yaml** - swagger doc
- **open-generator-config.yaml** - config for package
- **openapi-generator-cli.jar** - java cli for generating api

Run commands in **my_api** folder:

- `java -jar openapi-generator-cli.jar generate -i petstore.yaml -g dart -c open-generator-config.yaml --enable-post-process-file`
- `flutter pub get`

In main **pubspec.yaml** add

```yaml
dependencies:
  ...
  my_api:
    path: ./my_api
  ...
```

### Usage in dart code:

```dart
import 'package:my_api/api.dart';
...
final api = PetApi();
api.getPetById(1).then((value) => print(value));
```

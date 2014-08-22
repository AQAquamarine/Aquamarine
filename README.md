![](https://dl.dropboxusercontent.com/u/7817937/_github/aquamarine/aquamarine_logo.png)

Aquamarine
==========

Aquamarine iOS Model Framework

Built on

- AquaModel (inherits Mantle) - An improved model class. Non nil parameters & Better view-model binding support & Observable.
- [Aquasync](https://github.com/AQAquamarine/Aquasync) - An effortless data synchronization framework.
- AquaCollection (inherits [oxen](https://github.com/jacksonh/oxen)) - A collection focused on convinience of handling models. (re-order, filtering, scope, serialization, observation...)

and works well with

- ReactiveCocoa
- CoreData

Features
---

- **Effortless API handling**
- **Effortless Synchronization**
- **Effortless View-Model binding**

Breaking down...

- Effortless data storing / querying.
- Model serialization / deserialization from JSON, plist or msgpack.
- Transparently handling of resource through network like ActiveResource.
- Model <=> Backend sychronization and comprehensive protocols.
- Model collections which works well with TableView / CollectionView.
- Model <=> View Binding mechanism or handling KVO transparently.

Code Example
---

```objc
Album *album = [Album createWithJSON:json];
```

```objc
[Album get:13 completion:^{
    ...
} error:nil];
```

```objc
AQMValidationResult *result = [album validate];
```

```objc
[Album sync];
```

```objc
[album bind:view];
```

```objc
[albums bindCollectionView:collectionView]; // Will bind insertion, deletion, swapment, reloadData of collection into collectionView.
```

```objc
[albums cellAt:indexPath]; // It will handle EVERYTHING behalf of you. Just call this on your CollectionView DataSource.
```

```objc
[albums filter:@"location == 'Hawaii'"];
```

Declarative Style
---

```objc
// Album.m

+ (NSDictionary *)validationRules {
    return @{
        @"title": @[[AQMValidator presence], [AQMValidator shorterThan:256]]
    };
}

+ (NSDictionary *)JSONKeyMap {
    return @{
        @"title": @"title",
        @"createdAt": @"created_at",
        @"updatedAt": @"updated_at"
    };
}

+ (NSArray *)beforeSave {
    return @[@selector(doSomePreparationForSave)];
}
```

And advanced options...

```objc
// @Optional
+ (NSString *)resourcePath {
    return @"/albums"; 
}

// @Optional
+ (NSDictionary *)requestMap {
    return @{
        AquamarineRequestShow: @"GET /:id",
        AquamarineRequestCreate: @"POST /",
        AquamarineRequestUpdate: @"PATCH /:id",
        AquamarineRequestDestroy: @"DELETE /:id"
    };
}
```

Status
---

Perfectly WIP.

Related Projects
---

- [Proton](https://github.com/bitswift/Proton) - Model framework for Cocoa and Cocoa Touch applications
- [Mantle](https://github.com/Mantle/Mantle) - Model framework for Cocoa and Cocoa Touch

LICENSE
---

The MIT License (MIT)

Copyright (c) 2014 kaiinui

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

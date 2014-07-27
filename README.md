![](https://dl.dropboxusercontent.com/u/7817937/_github/aquamarine/aquamarine_logo.png)

Aquamarine
==========

Aquamarine iOS Model Framework

Built on

- AquaModel (inherits Mantle) - an improved model class. non nil parameters / better view-model binding support / observable.
- AquaRequest (based on AFNetworking) - a request manager focused on convinience of handling APIs. (re-send, caching, offline support, spinners...)
- [Aquasync](https://github.com/AQAquamarine/Aquasync) - an effortless data synchronization framework.
- AquaCollection (inherits KXCollection) - a collection focused on convinience of handling models. (re-order, filtering, observation...)

and works well with

- ReactiveCocoa
- Realm

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

Status
---

Perfectly WIP.

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

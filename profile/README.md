# qt-qaengine

Automation for Qt applications. The library runs inside the process under test and exposes the live interface over a TCP socket. The inspector and the driver are clients of that socket. This is not an official Qt module, and it is not [qt/qtqa](https://github.com/qt/qtqa).

## Projects

| Repository | What it is |
| --- | --- |
| [qt-qaengine](https://github.com/qt-qaengine/qt-qaengine) | In-process library. Listens on port `8900` (`QTQAENGINE_PORT`). Headers are `qtqaengine/`, the CMake target is `QtQaEngine::QtQaEngineLib`, the binary is `libqtqaengine.so` or `qtqaengine.dll`. |
| [qt-qaengine-inspector](https://github.com/qt-qaengine/qt-qaengine-inspector) | Desktop application that connects to a running library and shows the object tree. |
| [qt-qaengine-driver](https://github.com/qt-qaengine/qt-qaengine-driver) | Appium 2 driver `qtqaengine` (`automationName` `QtQaEngine`) and the MCP server `qt-qaengine-mcp`. The npm package is `appium-qt-qaengine-driver`. |

A client must send `{"cmd":"hello","protocol":1}` before any other command. The library answers with `"product":"qt-qaengine"`. The wire format is documented in the library: [docs/protocol.md](https://github.com/qt-qaengine/qt-qaengine/blob/master/docs/protocol.md).

The library is not a component to ship inside a product. Tests and tools talk to it from outside the process.

## License

Noncommercial use of these repositories is under [PolyForm Noncommercial 1.0.0](../LICENSE).

[OPEN_SOURCE_GRANT](../OPEN_SOURCE_GRANT) is a separate permission. It lets you install, copy, and run this software to develop and test a program that is publicly available under an OSI-approved license or an FSF free-software license. A company may use that permission. It does not cover a proprietary program, including a proprietary program in the same repository or the same CI job. It does not allow shipping this software inside a product, and it does not allow relicensing it under the other program's license.

Copyright (c) 2026 Andrei Kozhevnikov. The required notice is in [NOTICE](../NOTICE). Each project repository carries the same three files.

## Commercial Licensing

Using these projects in commercial products requires a separate license. Contact me at [coderus@duck.com](mailto:coderus@duck.com) and on Telegram at [https://t.me/icoderus](https://t.me/icoderus) to discuss pricing and terms. I also provide paid services for integrating automated tests into your infrastructure.

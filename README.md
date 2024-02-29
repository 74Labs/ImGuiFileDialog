[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/Iam1337/ImGui-FileDialog/blob/master/LICENSE)

# File Dialog for Dear ImGui

Simple file dialog for Dear ImGui. Based on [L2DFileDialog](https://github.com/Limeoats/L2DFileDialog).

Added fixes for Dear ImGui version: 1.90.4-docking.

![File Dialog](/screenshots/screen1.png?raw=true)

### Usage

Add `imgui_filedialog.h` to your C++ project and include it where you use ImGui.

```c++
// Declare outside draw loop
bool m_fileDialogOpen;
ImFileDialogInfo m_fileDialogInfo;

// App logic
if (ImGui::Button("Save File"))
{
    m_fileDialogOpen = true;
    m_fileDialogInfo.type = ImGuiFileDialogType_SaveFile;
    m_fileDialogInfo.title = "Save File";
    m_fileDialogInfo.fileName = "test.json";
    m_fileDialogInfo.directoryPath = std::filesystem::current_path();
}

// Any place in draw loop
if (ImGui::FileDialog(&m_fileDialogOpen, &m_fileDialogInfo))
{
    // Result path in: m_fileDialogInfo.resultPath
}
```

### Features
* Different file dialog types:
  * Open File
  * Save File
* Sort by:
  * File
  * Size
  * Type
  * Last modified date

### Changes
* Added SaveFile dialog type.
* Changed interface.
* Changed code style.

### License
This project is under the [Apache License](/LICENSE).

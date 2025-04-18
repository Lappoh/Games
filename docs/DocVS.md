# Документация по разработке игр в Visual Studio
## 1. Введение
Visual Studio (VS) — это профессиональная IDE от Microsoft, предоставляющая все необходимые инструменты для разработки игр: от написания кода до отладки и оптимизации. В этой документации рассмотрены ключевые аспекты создания игр, включая настройку среды, выбор движков, работу с графикой и публикацию проектов.
## 2. Настройка среды разработки
### 2.1. Установка Visual Studio
1. Скачайте Visual Studio 2022 Community (бесплатная версия) с официального сайта.
2. В установщике выберите workload's:
* Разработка игр на C++ (для Unreal Engine, DirectX, OpenGL).
* Разработка на .NET (для Unity, MonoGame).
* Разработка на Python (если используете Pygame).
3. Дополнительные компоненты:
  * Windows 10/11 SDK (для UWP-игр).
  * C++ CMake Tools (для сборки через CMake)
  * .NET Desktop Development (для WPF-игр).
### 2.2. Установка игровых движков
* Unity устанавливается через Unity Hub интегрируется через VS Автоматически (открытие .sln)
* Unreal Engine устанавливается через Epic Games Launcher интегрируется через VS требуя генерацию .sln
* Godot можно скачать с сайта Godot интегрируется через VS с поддержкой C# через .NET
* MonoGame устанавливается через dotnet new --install MonoGame.Templates.CSharp полная интегрируется через VS
## 3. Создание и настройка проекта
### 3.1. Для Unity
1. Создайте проект в Unity Hub.
2. Откройте скрипт в Visual Studio:
* Unity → Preferences → External Tools → Выберите VS 2022.
3. Отладка:
* Нажмите Attach to Unity (F5).
* Используйте Debug.Log() для вывода в консоль Unity.
### 3.2. Для Unreal Engine
1. Создайте проект в Unreal Editor.
2. Сгенерируйте файлы решения:
* File → Generate Visual Studio Project.
3. Открытие в VS:
* Запустите .sln файл.
* Для компиляции используйте Build Solution (F7).
### 3.3. Для MonoGame
1. Установите шаблоны:
* dotnet new --install MonoGame.Templates.CSharp
2. Создайте проект:
* dotnet new mgdesktopgl -n MyGame
3. Запустите в VS:
* Откройте .csproj и нажмите F5
## 4. Работа с графикой
### 4.1. DirectX (C++)
1. Создайте пустой проект C++.
2. Подключите библиотеки:
```
#include <d3d11.h>
#pragma comment(lib, "d3d11.lib")
```
3. Пример инициализации D3D11:
```
ID3D11Device* device = nullptr;
ID3D11DeviceContext* context = nullptr;
D3D11CreateDevice(nullptr, D3D_DRIVER_TYPE_HARDWARE, 0, 0, nullptr, 0, D3D11_SDK_VERSION, &device, nullptr, &context);
```
### 4.2. OpenGL (C++)
1. Установите GLFW и GLEW через vcpkg:
```
vcpkg install glfw3 glew
```
2. Пример кода:
```
#include <GL/glew.h>
#include <GLFW/glfw3.h>
```
### 4.3. Шейдеры (HLSL/GLSL)
* HLSL (DirectX):
```
// vertex.hlsl
float4 main(float3 pos : POSITION) : SV_POSITION {
    return float4(pos, 1.0);
}
```
* GLSL (OpenGL):
```
// fragment.glsl
#version 330 core
out vec4 FragColor;
void main() {
    FragColor = vec4(1.0, 0.0, 0.0, 1.0);
}
```

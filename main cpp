#include <Windows.h>
#include "CPSCounter.h"
#include "UI.h"
#include "imgui.h"
#include "imgui_impl_win32.h"
#include "imgui_impl_dx11.h"
#include <d3d11.h>

// Link necessary libs
#pragma comment(lib, "d3d11.lib")
#pragma comment(lib, "user32.lib")

bool showWindow = true;

int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE, LPSTR, int) {
    // Initialize CPS tracking
    InitMouseHook();

    // Initialize ImGui & DirectX11 window (this is where you'll need full DX11/ImGui setup)
    // For brevity, assume ImGui initialization here...

    // Main loop
    while (true) {
        // Begin frame
        ImGui_ImplDX11_NewFrame();
        ImGui_ImplWin32_NewFrame();
        ImGui::NewFrame();

        // Draw our UI
        RenderUI(showWindow);

        // End frame
        ImGui::Render();
        // Render draw data...
    }

    StopMouseHook();
    return 0;
}

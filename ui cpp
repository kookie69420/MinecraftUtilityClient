#include "UI.h"
#include "FullBright.h"
#include "CPSCounter.h"
#include "imgui.h"

void RenderUI(bool& showWindow) {
    if (!showWindow) return;

    ImGui::Begin("Minecraft Utility Client", &showWindow, ImGuiWindowFlags_AlwaysAutoResize);

    if (ImGui::Button("Enable Full Bright")) {
        EnableFullBright();
    }

    ImGui::Text("CPS: %d", GetCPS());

    if (ImGui::Button("Launch Minecraft")) {
        system("start shell:AppsFolder\\Microsoft.MinecraftUWP_8wekyb3d8bbwe!App");
    }

    ImGui::End();
}

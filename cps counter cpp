#include "CPSCounter.h"
#include <windows.h>
#include <vector>
#include <chrono>

std::vector<std::chrono::steady_clock::time_point> clicks;
HHOOK mouseHook;

LRESULT CALLBACK MouseProc(int nCode, WPARAM wParam, LPARAM lParam) {
    if (nCode == HC_ACTION && wParam == WM_LBUTTONDOWN) {
        auto now = std::chrono::steady_clock::now();
        clicks.push_back(now);
        clicks.erase(
            std::remove_if(clicks.begin(), clicks.end(), [now](auto t) {
                return std::chrono::duration_cast<std::chrono::milliseconds>(now - t).count() > 1000;
            }),
            clicks.end()
        );
    }
    return CallNextHookEx(mouseHook, nCode, wParam, lParam);
}

void InitMouseHook() {
    mouseHook = SetWindowsHookEx(WH_MOUSE_LL, MouseProc, NULL, 0);
}

void StopMouseHook() {
    UnhookWindowsHookEx(mouseHook);
}

int GetCPS() {
    return static_cast<int>(clicks.size());
}

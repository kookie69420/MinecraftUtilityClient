#include "FullBright.h"
#include <fstream>
#include <string>
#include <iostream>
#include <filesystem>

void EnableFullBright() {
    std::string path = std::getenv("LOCALAPPDATA");
    path += "\\Packages\\Microsoft.MinecraftUWP_8wekyb3d8bbwe\\LocalState\\games\\com.mojang\\minecraftpe\\options.txt";

    std::ifstream infile(path);
    if (!infile.is_open()) return;

    std::string content, line;
    while (std::getline(infile, line)) {
        if (line.find("gfx_gamma:") == 0) {
            content += "gfx_gamma:1000.0\n";
        } else {
            content += line + "\n";
        }
    }
    infile.close();

    std::ofstream outfile(path);
    outfile << content;
    outfile.close();
}

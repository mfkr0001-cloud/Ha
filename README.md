# GD Tools - Replay Lab (Android32 + Android64)

This ZIP contains the corrected project files for GitHub Actions builds of the Geode mod.

## Use
1. Extract this ZIP.
2. Upload the extracted files and folders to the root of `mfkr0001-cloud/Mega-Hacker` (not the ZIP itself).
3. Keep the folder `.github/workflows/` and the file `build.yml` inside it.
4. `CMakeLists.txt` belongs in the repository root, beside `mod.json`. Do NOT paste CMake code into `.github/workflows/*.yml`.
5. Commit the changes, then open GitHub Actions and run **Build Android Geode mod**.
6. Download the artifacts `GDTools-Android64` and `GDTools-Android32` from a successful run.

The workflow runs both Android targets separately. This ZIP fixes the CMake configuration error where `GDToolsReplayLab` was not a defined target before `setup_geode_mod()`. A successful compile has not been verified in this environment; if another compiler error appears, it will need its own fix.

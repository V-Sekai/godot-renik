# Godot RenIK

RenIK (Ren Inverse Kinematics) is a GDExtension for Godot 4 that provides advanced inverse kinematics for character animation.

## Features

- Full-body IK system for humanoid characters
- Spine IK with configurable curves and stiffness
- Arm and leg IK with twist controls
- Foot placement system with gait cycles
- Hip placement for natural movement
- Support for multiple bone chains and limbs

## Requirements

- Godot 4.1 or later
- SConstruct (for building locally)
- godot-cpp (included as submodule)

## Building

1. Clone the repository with submodules:
```bash
git clone --recursive https://github.com/yourusername/godot-renik.git
```

2. Build the extension:
```bash
cd godot-renik
./scripts/build.sh
```

Or manually:
```bash
scons target=template_release generate_bindings=no arch=universal precision=single
```

## Installation

Copy the `bin/addons/godot_renik` folder to your Godot project's `addons` directory, then enable the plugin in Project Settings.

## Usage

Add a `RenIK` node to your scene and configure it with your skeleton. See the documentation for detailed usage instructions.

## Documentation

The extension includes integrated documentation that automatically appears in Godot's built-in help system. When you build the extension with `target=template_release` (or `template_debug`/`editor`), the documentation from `doc_classes/*.xml` files is automatically compiled and included.

To view the documentation:
1. Open Godot editor
2. Go to Help → Search Help or press `F1`
3. Search for "RenIK", "RenIKChain", or "RenIKLimb"
4. The full class documentation will appear with all methods, properties, and descriptions

## License

See LICENSE file for details.


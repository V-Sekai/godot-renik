#!/usr/bin/env python
import os
import sys

env = SConscript("thirdparty/godot-cpp/SConstruct")

env.Append(
    CPPDEFINES=[
        "RENIK_BUILD",
    ]
)

env.Prepend(CPPPATH=["thirdparty", "include"])
env.Append(CPPPATH=["src/", "src/renik/"])
sources = [Glob("src/*.cpp")]
sources.extend([Glob("src/renik/*.cpp")])

# Generate documentation from XML files (for editor and template builds)
if env["target"] in ["editor", "template_debug", "template_release"]:
    doc_data = env.GodotCPPDocData("src/gen/doc_data.gen.cpp", source=Glob("doc_classes/*.xml"))
    sources.append(doc_data)

if env["platform"] == "macos" or env["platform"] == "ios":
	library = env.SharedLibrary(
		"bin/addons/godot_renik/bin/libgodot_renik{}.framework/libgodot_renik{}".format(
			env["suffix"], env["suffix"]
		),
		source=sources,
	)
elif env["platform"] == "ios":
	library = env.SharedLibrary(
		"bin/addons/godot_renik/bin/libgodot_renik{}.framework/libgodot_renik{}".format(
			env["suffix"], env["suffix"]
		),
		source=sources,
	)
else:
	library = env.SharedLibrary(
		"bin/addons/godot_renik/bin/libgodot_renik{}{}".format(env["suffix"], env["SHLIBSUFFIX"]),
		source=sources,
	)
Default(library)


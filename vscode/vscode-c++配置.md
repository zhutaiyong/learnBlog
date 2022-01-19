tasks.json 主要用于编译

{
        "version": "2.0.0",

        "tasks": [

                {
                        "type": "shell",

                        "label": "rs_debug",

                        "command": "cd ./DebugBuild ; make -j 4",// 编译

                        "args": [],

                        "options": {},

                        "problemMatcher": [],

                        "group": "build"

                },

                {
                        "type": "shell",

                        "label": "rs_release",

                        "command": "cd ./ReleaseBuild ; make -j 4", //编译

                        "args": [],

                        "options": {},

                        "problemMatcher": [],

                        "group": "build"

                }

        ]

}

launch.json 主要用于设置 程序 调试

{
        "version": "0.2.0",

        "configurations": [

        {
                "name": "rs_debug_name",

                "type": "cppdbg",

                "request": "launch",

                "program": "${workspaceFolder}/DebugBuild/dist/程序名",//输入需要调试的程序名称

                "args": [ //设置启动参数

                        "--conf",

                        "./configs/config.json",

                ],

                "stopAtEntry": false,

                "cwd": "${workspaceFolder}/DebugBuild/dist",

                "environment": [

                {
                        "name": "LD_LIBRARY_PATH",//设置环境变量

                        "value": "/home/dx/data/files/vcpkg/vcpkg/installed/x64-linux/lib:/home/dx/data/files/vcpkg/vcpkg/installed/x64-linux/debug/lib:/home/dx/data/works/Depends/osg-3.6.5/Debug/lib:/home/dx/data/works/Depends/osgQt/Debug/lib64:/home/dx/software/qt/5.9.7/gcc_64/lib:/home/dx/data/works/Depends/osgearth/Debug/lib64:/home/dx/data/works/Depends/grpc/lib",

                }

                ],

                "externalConsole": false,

                "MIMode": "gdb",

                "setupCommands": [

                {
                        "description": "为 gdb 启用整齐打印",

                        "text": "-enable-pretty-printing",

                        "ignoreFailures": true

                }

                ],

                "preLaunchTask": "rs_debug",

                "miDebuggerPath": "/usr/bin/gdb"

        },

        {
                "name": "rs_release_name",

                "type": "cppdbg",

                "request": "launch",

                "program": "${workspaceFolder}/ReleaseBuild/dist/程序名",

                "args": [

                ],

                "stopAtEntry": false,

                "cwd": "${workspaceFolder}/ReleaseBuild/dist",

                "environment": [

                {
                        "name": "LD_LIBRARY_PATH",

                        "value": "/home/dx/data/files/vcpkg/vcpkg/installed/x64-linux/lib:/home/dx/data/works/Depends/osg-3.6.5/Release/lib:/home/dx/data/works/Depends/osgQt/Release/lib64:/home/dx/software/qt/5.9.7/gcc_64/lib:/home/dx/data/works//Depends/osgearth/Release/lib64:/home/dx/data/works//Depends/grpc/lib",

                }

                ],

                "externalConsole": false,

                "MIMode": "gdb",

                "setupCommands": [

                {
                        "description": "为 gdb 启用整齐打印",

                        "text": "-enable-pretty-printing",

                        "ignoreFailures": true

                }

                ],

                "preLaunchTask": "rs_release",

                "miDebuggerPath": "/usr/bin/gdb"

              }

        ]

}


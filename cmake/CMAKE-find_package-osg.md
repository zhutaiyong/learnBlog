set(OSG_DIR /home/dx/data/test/learnOsg/Depend/Debug)

find_package(OpenSceneGraph COMPONENTS osg osgViewer osgGA osgDB osgManipulator osgSim osgParticle osgText osgUtil osgWidget osgShadow osgFX REQUIRED)

include_directories( 
${PROJECT_BINARY_DIR} 
${CMAKE_SOURCE_DIR}
${OSG_DIR}/include
)

target_link_libraries(${PROJECT_NAME} Qt5::Core
Qt5::Gui
Qt5::Widgets
Qt5::OpenGL
Qt5::Network
Qt5::Xml
${OPENTHREADS_LIBRARY}
${OSGVIEWER_LIBRARY}
${OSGDB_LIBRARY}
${OSG_LIBRARY}
${OSGGA_LIBRARY}
${OSGMANIPULATOR_LIBRARY}
${OSGSIM_LIBRARY}
${OSGTEXT_LIBRARY}
${OSGUTIL_LIBRARY}
${OSGWIDGET_LIBRARY}
${OSGSHADOW_LIBRARY}
${OSGFX_LIBRARY}
${OSGPARTICLE_LIBRARY}
)

最后别忘了 运行程序 需要加 LD_LIBRARY_PATH 

LD_LIBRARY_PATH=/data/test/learnOsg/Depend/Debug/lib


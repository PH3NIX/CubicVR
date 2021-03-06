include_directories (include) 
include_directories (external/bullet-2.78/src) 

IF(WIN32)
add_definitions (-DGLEW_STATIC)
ENDIF(WIN32)

IF(PSP)
add_definitions(-DARCH_PSP)
include_directories (${PSPSDK_PATH}/include)
set (CMAKE_CXX_FLAGS "-g -Wall -fno-rtti")
ENDIF(PSP)

IF(CMAKE_HOST_UNIX)
IF(NOT PSP)
add_definitions (-DGLEW_STATIC)
ENDIF(NOT PSP)
ENDIF(CMAKE_HOST_UNIX)

IF(CMAKE_COMPILER_IS_GNUCXX)
IF(NOT PSP)
#SET (CMAKE_CXX_FLAGS "-g -Wall -fno-inline-functions-called-once ")
ENDIF(NOT PSP)
ENDIF(CMAKE_COMPILER_IS_GNUCXX)

SET(CubicVR_SRCS
  source/AreaLight.cpp
  source/Bitmap.cpp
  source/BITSET.cpp
  source/Bone.cpp
  source/BSP.cpp
  source/Camera.cpp
  source/CollisionMap.cpp
  # source/Console.cpp
  source/Curve.cpp
  source/datatree/DataTree.cpp
  source/Envelope.cpp
  source/Face.cpp
  source/Font.cpp
  source/FRUSTUM.cpp
  # source/GameObject.cpp
  # source/Gamepad.cpp
  # source/Gamepad_360.cpp
  source/GLExt.cpp
  source/GLShader.cpp
  source/HDR.cpp
  source/IFFReader.cpp
  source/IMAGE.cpp
  source/Light.cpp
  source/lodepng.cpp
  source/Logger.cpp
  source/mat4.cpp
  source/Material.cpp
  source/math/MATRIX4X4.cpp
  source/math/PLANE.cpp
  # source/math/VECTOR2D.cpp
  source/math/VECTOR3D.cpp
  source/math/VECTOR4D.cpp
  source/Matrix.cpp
  source/Motion.cpp
  # source/networklib/ClientSocket.cpp
  # source/networklib/ClientSocket.h
  # source/networklib/ServerSocket.cpp
  # source/networklib/ServerSocket.h
  # source/networklib/Socket.cpp
  # source/networklib/Socket.h
  # source/networklib/test.cpp
  source/Object.cpp
  source/ObjectController.cpp
  source/objectLWO.cpp
  source/Particle.cpp
  source/ParticleEmitter.cpp
  source/ParticleSystem.cpp
  source/Pencil.cpp
  source/perlin.cpp
  source/ph/ph.cpp
  source/ProceduralObject.cpp
  source/ProceduralTexture.cpp
  source/Resource.cpp
  source/ResourceManager.cpp
  source/ResourcePool.cpp
  source/ResourceScene.cpp
  source/RGB.cpp
  source/RGBA.cpp
  source/RigidScene.cpp
  source/RigidSceneDebug.cpp
  source/Scene.cpp
  source/sceneCollada.cpp
  source/sceneLWS.cpp
  source/SceneObject.cpp
  source/SceneObjects/BSPSceneObject.cpp
  source/SceneObjects/Landscape.cpp
  source/SceneObjects/RigidBox.cpp
  source/SceneObjects/RigidCapsule.cpp
  source/SceneObjects/RigidSceneObject.cpp
  source/SceneObjects/RigidSphere.cpp
  source/SceneObjects/SoftSceneObject.cpp
  source/SceneObjects/Vehicle.cpp
  # source/Script.cpp
  source/SectorMap.cpp
  source/Shader.cpp
  source/SoftScene.cpp
  source/StringTokenizer.cpp
  source/StringUtil.cpp
  source/systemfont.cpp
  source/Texture.cpp
  source/Timer.cpp
  source/tinyxml/tinystr.cpp
  source/tinyxml/tinyxml.cpp
  source/tinyxml/tinyxmlerror.cpp
  source/tinyxml/tinyxmlparser.cpp
  source/Transform.cpp
  source/UV.cpp
  source/UVMapper.cpp
  source/Vector.cpp
  source/XYZ.cpp
  source/XYZRGB.cpp
)

SET (CubicVR_HDRS
  include/CubicVR/cvr_defines.h
  include/CubicVR/AreaLight.h
  include/CubicVR/Bitmap.h
  include/CubicVR/BITSET.h
  include/CubicVR/Bone.h
  include/CubicVR/BSP.h
  include/CubicVR/Camera.h
  include/CubicVR/CollisionMap.h
  # include/CubicVR/Console.h
  include/CubicVR/Curve.h
  include/CubicVR/datatree/DataTree.h
  include/CubicVR/Envelope.h
  include/CubicVR/Face.h
  include/CubicVR/Font.h
  include/CubicVR/FRUSTUM.h
  # include/CubicVR/GameObject.h
  # include/CubicVR/Gamepad.h
  # include/CubicVR/Gamepad_360.h
  include/CubicVR/GLExt.h
  include/CubicVR/GLShader.h
  include/CubicVR/HDR.h
  include/CubicVR/IFFReader.h
  include/CubicVR/IMAGE.h
  include/CubicVR/Light.h
  include/CubicVR/lodepng.h
  include/CubicVR/Logger.h
  include/CubicVR/Material.h
  include/CubicVR/mat4.h
  include/CubicVR/map_string.h
  include/CubicVR/math/MATRIX4X4.h
  include/CubicVR/math/PLANE.h
  # include/CubicVR/math/VECTOR2D.h
  include/CubicVR/math/VECTOR3D.h
  include/CubicVR/math/VECTOR4D.h
  include/CubicVR/Matrix.h
  include/CubicVR/Motion.h
  # include/CubicVR/networklib/ClientSocket.h
  # include/CubicVR/networklib/ClientSocket.h
  # include/CubicVR/networklib/ServerSocket.h
  # include/CubicVR/networklib/ServerSocket.h
  # include/CubicVR/networklib/Socket.h
  # include/CubicVR/networklib/Socket.h
  # include/CubicVR/networklib/test.h
  include/CubicVR/Object.h
  include/CubicVR/ObjectController.h
  include/CubicVR/objectLWO.h
  include/CubicVR/Particle.h
  include/CubicVR/ParticleEmitter.h
  include/CubicVR/ParticleSystem.h
  include/CubicVR/Pencil.h
  include/CubicVR/perlin.h
  include/CubicVR/ph/ph.h
  include/CubicVR/ProceduralObject.h
  include/CubicVR/ProceduralTexture.h
  include/CubicVR/Resource.h
  include/CubicVR/ResourceManager.h
  include/CubicVR/ResourcePool.h
  include/CubicVR/ResourceScene.h
  include/CubicVR/RGB.h
  include/CubicVR/RGBA.h
  include/CubicVR/RigidScene.h
  include/CubicVR/RigidSceneDebug.h
  include/CubicVR/Scene.h
  include/CubicVR/sceneCollada.h
  include/CubicVR/sceneLWS.h
  include/CubicVR/SceneObject.h
  include/CubicVR/SceneObjects/BSPSceneObject.h
  include/CubicVR/SceneObjects/Landscape.h
  include/CubicVR/SceneObjects/RigidBox.h
  include/CubicVR/SceneObjects/RigidCapsule.h
  include/CubicVR/SceneObjects/RigidSceneObject.h
  include/CubicVR/SceneObjects/RigidSphere.h
  include/CubicVR/SceneObjects/SoftSceneObject.h
  include/CubicVR/SceneObjects/Vehicle.h
  # include/CubicVR/Script.h
  include/CubicVR/SectorMap.h
  include/CubicVR/Shader.h
  include/CubicVR/SoftScene.h
  include/CubicVR/StringTokenizer.h
  include/CubicVR/StringUtil.h
  include/CubicVR/systemfont.h
  include/CubicVR/Texture.h
  include/CubicVR/Timer.h
  include/CubicVR/tinyxml/tinystr.h
  include/CubicVR/tinyxml/tinyxml.h
  include/CubicVR/Transform.h
  include/CubicVR/UV.h
  include/CubicVR/UVMapper.h
  include/CubicVR/Vector.h
  include/CubicVR/XYZ.h
  include/CubicVR/XYZRGB.h
)


SET (TinyJPEG_SRCS
  source/tinyjpeg/jidctflt.c
  source/tinyjpeg/tinyjpeg.c  
)

SET (TinyJPEG_HDRS
  include/CubicVR/tinyjpeg/tinyjpeg.h
  include/CubicVR/tinyjpeg/tinyjpeg-internal.h
)

IF(WIN32)
	SET(CubicVR_platform_SRCS source/textureTGA.cpp source/glew/glew.c)
	SET(CubicVR_platform_HDRS include/CubicVR/glew/glew.h include/CubicVR/glew/wglew.h)
ENDIF(WIN32)


IF(CMAKE_HOST_UNIX)
IF(NOT PSP)
	SET(CubicVR_platform_SRCS source/textureTGA.cpp source/glew/glew.c)
	SET(CubicVR_platform_HDRS include/CubicVR/glew/glew.h)
ENDIF(NOT PSP)
ENDIF(CMAKE_HOST_UNIX)

IF(PSP)
	SET(CubicVR_platform_SRCS source/psp/TGALoader.cpp)
	SET(CubicVR_platform_HDRS include/CubicVR/psp/TGALoader.h include/memory.h)
ENDIF(PSP)


add_library(cubicvr 
  ${CubicVR_SRCS}
  ${CubicVR_HDRS}
  ${TinyJPEG_SRCS}
  ${TinyJPEG_HDRS}
  ${CubicVR_platform_SRCS}
  ${CubicVR_platform_HDRS}
)

FILE(GLOB cubicvr_header_files "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/*.h")
INSTALL(FILES ${cubicvr_header_files} DESTINATION include/CubicVR/)

FILE(GLOB cubicvr_header_files1 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/datatree/*.h")
INSTALL(FILES ${cubicvr_header_files1} DESTINATION include/CubicVR/datatree/)

FILE(GLOB cubicvr_header_files2 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/math/*.h")
INSTALL(FILES ${cubicvr_header_files2} DESTINATION include/CubicVR/math/)

FILE(GLOB cubicvr_header_files3 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/SceneObjects/*.h")
INSTALL(FILES ${cubicvr_header_files3} DESTINATION include/CubicVR/SceneObjects/)

FILE(GLOB cubicvr_header_files4 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/tinyjpeg/*.h")
INSTALL(FILES ${cubicvr_header_files4} DESTINATION include/CubicVR/tinyjpeg/)

FILE(GLOB cubicvr_header_files5 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/tinyxml/*.h")
INSTALL(FILES ${cubicvr_header_files5} DESTINATION include/CubicVR/tinyxml/)

FILE(GLOB cubicvr_header_files6 "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/ph/*.h")
INSTALL(FILES ${cubicvr_header_files6} DESTINATION include/CubicVR/ph/)

FILE(GLOB cubicvr_shader_files "${CMAKE_CURRENT_SOURCE_DIR}/shaders/*.[fv]")
INSTALL(FILES ${cubicvr_shader_files} DESTINATION shaders)

IF(WIN32)
FILE(GLOB cubicvr_header_files_win "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/glew/*.h")
INSTALL(FILES ${cubicvr_header_files_win} DESTINATION include/CubicVR/glew/)
ENDIF(WIN32)

IF(CMAKE_HOST_UNIX)
IF(NOT PSP)
FILE(GLOB cubicvr_header_files_lin "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/glew/*.h")
INSTALL(FILES ${cubicvr_header_files_lin} DESTINATION include/CubicVR/glew/)
ENDIF(NOT PSP)
ENDIF(CMAKE_HOST_UNIX)

IF(PSP)
FILE(GLOB cubicvr_header_files_psp "${CMAKE_CURRENT_SOURCE_DIR}/include/CubicVR/psp/*.h")
INSTALL(FILES ${cubicvr_header_files_psp} DESTINATION include/CubicVR/psp/)

FILE(GLOB cubicvr_header_missing_psp "${CMAKE_CURRENT_SOURCE_DIR}/include/memory.h")
INSTALL(FILES ${cubicvr_header_missing_psp} DESTINATION include/)
ENDIF(PSP)

INSTALL(TARGETS cubicvr
  ARCHIVE DESTINATION lib/
)


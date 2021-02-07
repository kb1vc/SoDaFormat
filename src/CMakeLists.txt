
########### next target ###############

set(FORMAT_SRCS
	Format.cxx
	)


IF(MACOSX) 
  add_library(sodaformat SHARED ${FORMAT_SRCS})
ELSE()
  add_library(sodaformat STATIC ${FORMAT_SRCS})
ENDIF()

install(TARGETS sodaformat DESTINATION lib)

# Export header files that are required to build loadable modules

install(FILES ../include/Format.hxx DESTINATION "include/SoDa")

add_executable(Format_Test Format_Test.cxx)
target_link_libraries(Format_Test sodaformat)



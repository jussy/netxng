############################################################################
# CMakeLists.txt file for building ROOT net/netxng package
# @author Lukasz Janyst <ljanyst@cern.ch>
############################################################################

include_directories(${XROOTD_INCLUDE_DIR})
add_definitions(${XROOTD_CFLAGS})

ROOT_GENERATE_DICTIONARY(G__NetXNG *.h LINKDEF LinkDef.h)
ROOT_GENERATE_ROOTMAP(NetXNG LINKDEF LinkDef.h DEPENDENCIES RIO Thread)
ROOT_LINKER_LIBRARY(NetXNG *.cxx G__NetXNG.cxx LIBRARIES ${XROOTD_LIBRARIES} DEPENDENCIES RIO Thread)

ROOT_INSTALL_HEADERS()


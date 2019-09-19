project(acctcreator)

set(EOSIO_WASM_OLD_BEHAVIOR "Off")
find_package(eosio.cdt)

add_contract( acctcreator acctcreator acctcreator.cpp )
target_include_directories( acctcreator PUBLIC ${CMAKE_SOURCE_DIR}/../include )
target_ricardian_directory( acctcreator ${CMAKE_SOURCE_DIR}/../ricardian )
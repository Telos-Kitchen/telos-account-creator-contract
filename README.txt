--- acctcreator Project ---

 - How to Build -
   - cd to 'build' directory
   - run the command 'cmake ..'
   - run the command 'make'

 - After build -
   - The built smart contract is under the 'acctcreator' directory in the 'build' directory
   - You can then do a 'set contract' action with 'cleos' and point in to the './build/acctcreator' directory

 - Additions to CMake should be done to the CMakeLists.txt in the './src' directory and not in the top level CMakeLists.txt



cleos -u https://test.telos.kitchen push action eosio updateauth '{
    "account": "tksmscreator",
    "permission": "active",
    "parent": "owner",
    "auth": {
        "keys": [ {
            "key": "EOS55SX8h8i8NVrdMcEqk3ap2W3axmp6hoYAEwb351v5wWEU4uaFq",
            "weight": 1 }
        ],
        "threshold": 1,
        "accounts": [
            {
                "permission": {
                    "actor": "tksmscreator",
                    "permission": "eosio.code"
                },
                "weight": 1
            }
        ],
        "waits": []
    }
}' -p tksmscreator@owner

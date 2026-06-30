cmake_minimum_required(VERSION 3.15)

project(CPP_Derivative_Pricing_Engine)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(include)

set(COMMON_SOURCES
    src/options/Option.cpp
    src/options/EuropeanOption.cpp
    src/options/AsianOption.cpp
    src/pricers/BlackScholesPricer.cpp
    src/pricers/MonteCarloPricer.cpp
)

add_executable(main_test
    main.cpp
    ${COMMON_SOURCES}
)

add_executable(bs_price_greeks_vs_spot
    examples/bs_price_greeks_vs_spot.cpp
    ${COMMON_SOURCES}
)

add_executable(mc_convergence
    examples/mc_convergence.cpp
    ${COMMON_SOURCES}
)

add_executable(mc_repeated_estimates
    examples/mc_repeated_estimates.cpp
    ${COMMON_SOURCES}
)

add_executable(asian_arithmetic_vs_geometric
    examples/asian_arithmetic_vs_geometric.cpp
    ${COMMON_SOURCES}
)

add_executable(asian_monitoring_dates
    examples/asian_monitoring_dates.cpp
    ${COMMON_SOURCES}
)

add_executable(asian_vs_european
    examples/asian_vs_european.cpp
    ${COMMON_SOURCES}
)
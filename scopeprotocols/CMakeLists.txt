include_directories(${GTKMM_INCLUDE_DIRS} ${SIGCXX_INCLUDE_DIRS})
link_directories(${GTKMM_LIBRARY_DIRS} ${SIGCXX_LIBRARY_DIRS})

set(SCOPEPROTOCOLS_SOURCES
	ACCoupleDecoder.cpp
	CANDecoder.cpp
	ClockJitterDecoder.cpp
	ClockRecoveryDecoder.cpp
	ClockRecoveryDebugDecoder.cpp
	DCOffsetDecoder.cpp
	DDR3Decoder.cpp
	DifferenceDecoder.cpp
	DVIDecoder.cpp
	Ethernet10BaseTDecoder.cpp
	Ethernet100BaseTDecoder.cpp
	EthernetAutonegotiationDecoder.cpp
	EthernetGMIIDecoder.cpp
	EthernetProtocolDecoder.cpp
	EyeDecoder2.cpp
	FFTDecoder.cpp
	I2CDecoder.cpp
	IBM8b10bDecoder.cpp
	JtagDecoder.cpp
	MDIODecoder.cpp
	MovingAverageDecoder.cpp
	ParallelBusDecoder.cpp
	PeriodMeasurementDecoder.cpp
	SincInterpolationDecoder.cpp
	ThresholdDecoder.cpp
	TMDSDecoder.cpp
	UARTDecoder.cpp
	UartClockRecoveryDecoder.cpp
	USB2ActivityDecoder.cpp
	USB2PacketDecoder.cpp
	USB2PCSDecoder.cpp
	USB2PMADecoder.cpp
	WaterfallDecoder.cpp

	AverageStatistic.cpp
	MaximumStatistic.cpp
	MinimumStatistic.cpp

	scopeprotocols.cpp
	)

add_library(scopeprotocols SHARED
	${SCOPEPROTOCOLS_SOURCES})

target_link_libraries(scopeprotocols
	${LIBFFTS_LIBRARIES})

target_include_directories(scopeprotocols
PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
PRIVATE ${LIBFFTS_INCLUDE_DIR})

install(TARGETS scopeprotocols LIBRARY DESTINATION /usr/lib)

cmake_minimum_required(VERSION 2.6)
project(cmod)

set(CMAKE_CXX_COMPILER g++)
set(PROJECT_VERSION_MAJOR 0)
set(PROJECT_VERSION_MINOR 0)

set(CMAKE_CXX_STANDARD 11)

set(SRC_DIR ./)
set(SYSTEMC_HOME /home/local/SPREADTRUM/binguang.zhao/tools/systemc/systemc-2.3.0a)
set(SYSTEMC_INC_DIR ${SYSTEMC_HOME}/include)
set(SYSTEMC_LIB_DIR ${SYSTEMC_HOME}/lib-linux64)

add_definitions(-MMD -MP -fPIC -Wall -Werror -DSC_INCLUDE_DYNAMIC_PROCESSES -Wp,-w)

INCLUDE_DIRECTORIES(
	./include
	${SRC_DIR}/include/nvdla_ness_header
	${SRC_DIR}/include
	${SRC_DIR}/nvdla_payload
	${SRC_DIR}/bdma
	${SRC_DIR}/cacc
	${SRC_DIR}/cbuf
	${SRC_DIR}/cdma
	${SRC_DIR}/cdp
	${SRC_DIR}/cmac
	${SRC_DIR}/csb_master
	${SRC_DIR}/csc
	${SRC_DIR}/cvif
	${SRC_DIR}/glb
	${SRC_DIR}/hls_wrapper
	${SRC_DIR}/mcif
	${SRC_DIR}/nvdla_core
	${SRC_DIR}/pdp
	${SRC_DIR}/rubik
	${SRC_DIR}/sdp
	${SRC_DIR}/bdma/gen
	${SRC_DIR}/cacc/gen
	${SRC_DIR}/cbuf/gen
	${SRC_DIR}/cdma/gen
	${SRC_DIR}/cdp/gen
	${SRC_DIR}/cmac/gen
	${SRC_DIR}/csb_master/gen
	${SRC_DIR}/csc/gen
	${SRC_DIR}/cvif/gen
	${SRC_DIR}/glb/gen
	${SRC_DIR}/hls_wrapper/gen
	${SRC_DIR}/mcif/gen
	${SRC_DIR}/nvdla_core/gen
	${SRC_DIR}/pdp/gen
	${SRC_DIR}/rubik/gen
	${SRC_DIR}/sdp/gen
	${SRC_DIR}/hls/include
	${SRC_DIR}/hls/cdma_libs
	${SRC_DIR}/hls/cdp_libs
	${SRC_DIR}/hls/csc_libs
	${SRC_DIR}/hls/sdp
	${SRC_DIR}/hls/vlibs
	${SYSTEMC_INC_DIR})

set(SRC_LIST
	${SRC_DIR}/nvdla_payload/dla_b_transport_payload.cpp
	${SRC_DIR}/nvdla_payload/gp_mm.cpp
	${SRC_DIR}/bdma/NV_NVDLA_bdma.cpp
	${SRC_DIR}/bdma/BdmaCore.cpp
	${SRC_DIR}/bdma/gen/bdma_reg_model.cpp
	${SRC_DIR}/cacc/NV_NVDLA_cacc.cpp
	${SRC_DIR}/cacc/gen/cacc_reg_model.cpp
	${SRC_DIR}/cbuf/NV_NVDLA_cbuf.cpp
	${SRC_DIR}/cdma/NV_NVDLA_cdma.cpp
	${SRC_DIR}/cdma/gen/cdma_reg_model.cpp
	${SRC_DIR}/cdp/NV_NVDLA_cdp.cpp
	${SRC_DIR}/cdp/gen/cdp_reg_model.cpp
	${SRC_DIR}/cdp/gen/cdp_rdma_reg_model.cpp
	${SRC_DIR}/cmac/NV_NVDLA_cmac.cpp
	${SRC_DIR}/cmac/gen/cmac_a_reg_model.cpp
	${SRC_DIR}/csb_master/gen/NV_NVDLA_csb_master.cpp
	${SRC_DIR}/csc/NV_NVDLA_csc.cpp
	${SRC_DIR}/csc/gen/csc_reg_model.cpp
	${SRC_DIR}/cvif/gen/NV_NVDLA_cvif.cpp
	${SRC_DIR}/glb/NV_NVDLA_glb.cpp
	${SRC_DIR}/glb/gen/glb_reg_model.cpp
	${SRC_DIR}/glb/gen/gec_reg_model.cpp
	${SRC_DIR}/hls_wrapper/cdma_hls_wrapper.cpp
	${SRC_DIR}/hls_wrapper/cdp_hls_wrapper.cpp
	${SRC_DIR}/hls_wrapper/cdp_icvt_wrapper.cpp
	${SRC_DIR}/hls_wrapper/cdp_ocvt_wrapper.cpp
	${SRC_DIR}/hls_wrapper/csc_hls_wrapper.cpp
	${SRC_DIR}/hls_wrapper/pdp_hls_wrapper.cpp
	${SRC_DIR}/hls_wrapper/sdp_hls_wrapper.cpp
	${SRC_DIR}/mcif/gen/NV_NVDLA_mcif.cpp
	${SRC_DIR}/nvdla_clibs/NvdlaDataFormatConvertor.cpp
	${SRC_DIR}/nvdla_core/NV_NVDLA_core.cpp
	${SRC_DIR}/nvdla_core/NvdlaCoreDummy.cpp
	${SRC_DIR}/nvdla_top/NV_nvdla.cpp
	${SRC_DIR}/nvdla_top/NvdlaAxiAdaptor.cpp
	${SRC_DIR}/nvdla_top/NvdlaCsbAdaptor.cpp
	${SRC_DIR}/nvdla_top/NvdlaTopDummy.cpp
	${SRC_DIR}/pdp/NV_NVDLA_pdp.cpp
	${SRC_DIR}/pdp/gen/pdp_reg_model.cpp
	${SRC_DIR}/pdp/gen/pdp_rdma_reg_model.cpp
	${SRC_DIR}/rubik/NV_NVDLA_rbk.cpp
	${SRC_DIR}/rubik/gen/rbk_reg_model.cpp
	${SRC_DIR}/sdp/NV_NVDLA_sdp.cpp
	${SRC_DIR}/sdp/gen/sdp_reg_model.cpp
	${SRC_DIR}/sdp/gen/sdp_rdma_reg_model.cpp
	${SRC_DIR}/hls/cdma_libs/cdma_cvt.cpp
	${SRC_DIR}/hls/cdp_libs/cdp_icvt.cpp
	${SRC_DIR}/hls/cdp_libs/cdp_ocvt.cpp
	${SRC_DIR}/hls/csc_libs/csc_cvt.cpp
	${SRC_DIR}/hls/sdp/sdp_x.cpp
	${SRC_DIR}/hls/sdp/sdp_y_core.cpp
	${SRC_DIR}/hls/sdp/sdp_y_idx.cpp
	${SRC_DIR}/hls/sdp/sdp_y_cvt.cpp
	${SRC_DIR}/hls/sdp/sdp_c.cpp
	${SRC_DIR}/hls/sdp/sdp_y.cpp
	${SRC_DIR}/hls/sdp/sdp_y_inp.cpp
	${SRC_DIR}/hls/vlibs/fp16_add.cpp
	${SRC_DIR}/hls/vlibs/fp16_max.cpp
	${SRC_DIR}/hls/vlibs/fp16_min.cpp
	${SRC_DIR}/hls/vlibs/fp16_mul.cpp
	${SRC_DIR}/hls/vlibs/fp16_sub.cpp
	${SRC_DIR}/hls/vlibs/fp16_to_fp17.cpp
	${SRC_DIR}/hls/vlibs/fp16_to_fp32.cpp
	${SRC_DIR}/hls/vlibs/fp17_add.cpp
	${SRC_DIR}/hls/vlibs/fp17_max.cpp
	${SRC_DIR}/hls/vlibs/fp17_min.cpp
	${SRC_DIR}/hls/vlibs/fp17_mul.cpp
	${SRC_DIR}/hls/vlibs/fp17_sub.cpp
	${SRC_DIR}/hls/vlibs/fp17_to_fp16.cpp
	${SRC_DIR}/hls/vlibs/fp17_to_fp32.cpp
	${SRC_DIR}/hls/vlibs/fp32_add.cpp
	${SRC_DIR}/hls/vlibs/fp32_mul.cpp
	${SRC_DIR}/hls/vlibs/fp32_sub.cpp
	${SRC_DIR}/hls/vlibs/fp32_to_fp16.cpp
	${SRC_DIR}/hls/vlibs/fp32_to_fp17.cpp
	${SRC_DIR}/hls/vlibs/uint16_to_fp17.cpp)

link_libraries(${SYSTEMC_LIB_DIR}/libsystemc-2.3.0.so)

add_library(nvdla_cmod SHARED ${SRC_LIST})
target_link_libraries(nvdla_cmod)

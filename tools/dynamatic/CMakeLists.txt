set(LLVM_LINK_COMPONENTS
  Support
)

add_llvm_tool(dynamatic
  dynamatic.cpp
)

llvm_update_compile_flags(dynamatic)
target_compile_definitions(dynamatic PRIVATE DYNAMATIC_ROOT="${CMAKE_SOURCE_DIR}")
target_link_libraries(dynamatic
  PRIVATE
  DynamaticSupport
  DynamaticTransforms

  DynamaticHandshake

  MLIRIR
  MLIRParser
  MLIRSupport
  MLIRPass
  MLIRLLVMDialect
  MLIRArithDialect
  MLIRMemRefDialect
  readline
  )

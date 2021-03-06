#
# Copyright 2018-present Barefoot Networks, Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

licenses(["notice"])  # Apache v2

load(
    "//bazel:rules.bzl",
    "STRATUM_INTERNAL",
    "stratum_cc_library",
    "stratum_cc_test",
    "HOST_ARCHES",
)

package(
    default_visibility = STRATUM_INTERNAL,
)

stratum_cc_library(
    name = "bmv2_switch",
    srcs = ["bmv2_switch.cc"],
    hdrs = ["bmv2_switch.h"],
    deps = [":bmv2_chassis_manager",
            "@com_google_googleapis//google/rpc:status_cc_proto",
            "//stratum/glue:integral_types",
            "//stratum/glue:logging",
            "//stratum/glue/status:status_macros",
            "//stratum/hal/lib/common:phal_interface",
            "//stratum/hal/lib/common:switch_interface",
            "//stratum/hal/lib/pi:pi_node",
            "//stratum/lib:constants",
            "//stratum/lib:macros",
            "@com_google_absl//absl/container:flat_hash_map",
            "//stratum/glue/gtl:map_util",
    ],
)

stratum_cc_library(
    name = "bmv2_chassis_manager",
    srcs = ["bmv2_chassis_manager.cc"],
    hdrs = ["bmv2_chassis_manager.h"],
    deps = ["@com_github_google_glog//:glog",
            "@com_google_absl//absl/base:core_headers",
            "@com_google_absl//absl/memory",
            "@com_google_absl//absl/synchronization",
            "@com_google_protobuf//:protobuf",
            "//stratum/glue:integral_types",
            "//stratum/glue:logging",
            "//stratum/glue/status",
            "//stratum/glue/status:statusor",
            "//stratum/hal/lib/common:common_cc_proto",
            "//stratum/hal/lib/common:constants",
            "//stratum/hal/lib/common:phal_interface",
            "//stratum/hal/lib/common:switch_interface",
            "//stratum/hal/lib/common:utils",
            "//stratum/hal/lib/common:writer_interface",
            "//stratum/lib:constants",
            "//stratum/lib:macros",
            "//stratum/lib:utils",
            "//stratum/public/lib:error",
            "//stratum/glue/gtl:map_util",
            "@local_bmv2_bin//:bmv2_headers",
            "@local_bmv2_bin//:bmv2_simple_switch",
    ],
)

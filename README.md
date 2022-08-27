

#include <iostream>

#define LOGURU_WITH_STREAMS 1
#define LOGURU_USE_FMTLIB 1

#include "loguru.cpp"
#include "loguru.hpp"
#include "loguru_example.hpp"

int main(int argc, char *argv[]) {
  loguru::init(argc, argv);
  loguru::add_file("everything.log", loguru::Append,
                   loguru::Verbosity_MAX); // Verbosity_INFO  Verbosity_MAX

  int a = 12312;

  LOG_S(INFO) << "Hello " << a;

  LOG_S(INFO) << fmt::format("Hello {}!\n", "world");
  LOG_S(WARNING) << fmt::format("Hello {}!\n", a);
  LOG_S(ERROR) << fmt::format("Hello {}!\n", a);

  return 0;
}

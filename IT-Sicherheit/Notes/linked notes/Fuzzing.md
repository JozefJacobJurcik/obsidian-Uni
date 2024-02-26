---

---

In programming and software development, **fuzzing** or *fuzz testing* is an automated software testing technique that involves *providing invalid, unexpected, or random data as inputs to a computer program*. The program is then monitored for exceptions such as crashes, failing built-in code assertions, or potential memory leaks. Typically, fuzzers are used to test programs that take structured inputs. This structure is specified, e.g., in a file format or protocol and distinguishes valid from invalid input. An effective fuzzer *generates semi-valid inputs that are "valid enough" in that they are not directly rejected by the parser*, but do create unexpected behaviors deeper in the program and are *"invalid enough" to expose corner cases that have not been properly dealt with*.

For the purpose of security, input that crosses a trust boundary is often the most useful. For example, it is more important to fuzz code that handles the upload of a file by any user than it is to fuzz the code that parses a configuration file that is accessible only to a privileged user. 
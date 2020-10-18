## Week 2

midterm, endterm - both must be passed

While language - check specification in Canvas
Looks like ADA to me (?)

# Lexical analysis, Flex

- Download lexical analyzer from canvas link
- requirement: flex, g++/clang (correct versions preinstalled on pandora)
- run make
- ./while tests/01.ok (should run without a problem)

extend it with fractional number
(\+|\-)?(0|([1-9][0-9]*))(\.[0-9]+)?	std::cout << "T_FRACTIONALNUM" << std::endl;

recognize time in hh:mm format
hh could be 00..23
mm could be 00..59
(([0-1][0-9])|(2[0-3]))\:([0-5][0-9])   std::cout << "T_TIME" << std::endl;

# TODO for next week
- [ ] how to express even number of digits
- [ ] how to express multiline comment


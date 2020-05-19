# java8
# 流
1 分组 Map<Integer,Integer> ret1 = teachers.stream().collect(Collectors.groupingBy(Teacher::getAge,Collectors.summingInt(Teacher::getAge)));


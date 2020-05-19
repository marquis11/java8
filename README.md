# java8
# 流
1 分组 Map<Integer,Integer> ret1 = teachers.stream().collect(Collectors.groupingBy(Teacher::getAge,Collectors.summingInt(Teacher::getAge)));
2 过滤 List<Teacher> ret =  teachers.stream().distinct().filter( t -> t.getAge()>=20).collect(Collectors.toList());

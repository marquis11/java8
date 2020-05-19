# java8
# 流
1 分组 Map<Integer,Integer> ret1 = teachers.stream().collect(Collectors.groupingBy(Teacher::getAge,Collectors.summingInt(Teacher::getAge)));
2 过滤 List<Teacher> ret =  teachers.stream().distinct().filter( t -> t.getAge()>=20).collect(Collectors.toList());
3 求和 BigDecimal salary =  teachers.stream().map(Teacher::getSalary).reduce(new BigDecimal("10000"),BigDecimal::add);//.get();
4 最值  BigDecimal salary =  teachers.stream().max((x,y) -> {
            if(x.getAge() != y.getAge()){
                return x.getAge() - y.getAge();
            } else {
                if(x.getSalary() != y.getSalary()){
                    return x.getSalary().compareTo(y.getSalary());
                }else {
                    return 1;
                }
            }

        }).get().getSalary();

    }
5 多属性排序 List<Teacher> ret = teachers.stream().sorted(Comparator.comparing(Teacher::getAge).reversed().thenComparing(Teacher::getSalary).reversed()).collect(Collectors.toList());

# Livemark Demo

## Data

```script
from frictionless import Resource

resource = Resource('https://raw.githubusercontent.com/frictionlessdata/livemark/main/data/cars.csv')
resource.write('data/cars.csv')
```

## Table

```table
data: data/cars.csv
filters: true
dropdownMenu: true
columnSorting:
  initialConfig:
    column: 2
    sortOrder: desc
width: 600
```

## Chart

```chart
data:
  url: data/cars.csv
mark: circle
selection:
  brush:
    type: interval
encoding:
  x:
    type: quantitative
    field: kmpl
    scale:
     domain: [12,25]
  y:
    type: quantitative
    field: price
    scale:
     domain: [100,900]
  color:
    condition:
      selection: brush
      field: type
      type: nominal
    value: grey
  size:
    type: quantitative
    field: bhp
width: 500
height: 300
```

## Conclusion

Hatchbacks are more green!


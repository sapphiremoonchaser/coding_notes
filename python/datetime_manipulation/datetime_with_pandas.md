## Convert Strings to Datetime in a DataFrame
  
`df['date'] = pd.to_datetime(df['date'])`

#### Specify a format
```aiignore
df['date'] = pd.to_datetime(
    df['date'],
    format="%Y-%m-%d"
)
```


# Extracting Components
```aiignore
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day'] = df['date'].dt.day
df['weekday'] = df['date'].dt.day_name()
df['hour'] = df['date'].dt.hour
```

## Converting Datetime -> Date Only
  
#### Drop the time part
`df['date_only'] = df['date'].dt.date`

#### Keep datetime dtype at midnight
`df['datetime_midnight'] = df['date'].dt.normalize()`


## Arithmetic in Pandas

`df['next_week'] = df['date'] + pd.Timedelta(days=7)`

#### Difference between rows
```aiignore
df['diff_days'] = (
    df['date'] - df['date'].shift(1)
).dt.days
```

## Filtering by date
   
```aiignore
df[
    df['date'] >= '2025-01-01'
]
```

#### with  timestamp
```aiignore
df[
    df['date'] >= pd.Timestamp(2024, 1, 1)
]
```

## Setting Datetime column as Index
  
`df = df.set_index('date').sort_index()`

## Handling missing datetime values

Invalid formats become `NaT`
  
```aiignore
df['date'] = pd.to-datetime(
    df['date'],
    errors='coerce
)
```


## Resampling (Time Series)
  
`monthly = df.resample('M').sum()`
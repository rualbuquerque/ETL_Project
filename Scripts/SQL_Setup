USE master
GO
--------------------///// CREATE DATABASE STM_SR //////-----------------------------------

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'STM_SRC')
DROP DATABASE STM_SRC

CREATE DATABASE STM_SRC




/****** Object:  Schema [stg]    ******/
USE [STM_SRC]
GO

CREATE SCHEMA [stg]
GO




----------------------////////////////////////////////////////////---------------------------------------
----------------------////////////////   STG TABLES     //////////---------------------------------------
----------------------////////////////////////////////////////////---------------------------------------

------------------////// CREATE stg.Error Table ///////-------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Error_Table]') IS NOT NULL
DROP TABLE [stg].[Error_Table]

CREATE TABLE [stg].[Error_Table] (
    [Error_MSG] varchar(100)
)


------------------////// CREATE stg.agency Table ///////-------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Agency]') IS NOT NULL
DROP TABLE [stg].[Agency]

CREATE TABLE [stg].[Agency] (
    [agency_id] varchar(50),
    [agency_name] varchar(50),
    [agency_url] varchar(50),
    [agency_timezone] varchar(50),
    [agency_lang] varchar(50),
    [agency_phone] varchar(50),
    [agency_fare_url] varchar(50)
)


-------------//////////// CREATE TABLE [stg].[Calendar_Dates_Staging]  //////////////----------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Calendar_Dates_Staging]') IS NOT NULL
DROP TABLE [stg].[Calendar_Dates_Staging]

CREATE TABLE [stg].[Calendar_Dates_Staging] (
    [service_id] varchar(50),
    [date] varchar(50),
    [exception_type] varchar(50)
)


-------------//////////// CREATE TABLE [stg].[Fare_Atributes] //////////////----------------
USE STM_SRC
GO


IF OBJECT_ID ('[stg].[Fare_Atributes]') IS NOT NULL
DROP TABLE [stg].[Fare_Atributes]


CREATE TABLE [stg].[Fare_Atributes](
	[fare_id] [varchar](50) NULL,
	[price] [varchar](50) NULL,
	[currency_type] [varchar](50) NULL,
	[payment_method] [varchar](50) NULL,
	[transfers] [varchar](50) NULL,
	[transfer_duration] [varchar](50) NULL
) 


------------//////// CREATE [stg].[fare_rules_Staging] //////////---------------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[fare_rules_Staging]') IS NOT NULL
DROP TABLE [stg].[fare_rules_Staging]

CREATE TABLE [stg].[fare_rules_Staging] (
    [fare_id] varchar(50),
    [route_id] varchar(50),
    [origin_id] varchar(50),
    [destination_id] varchar(50),
    [contains_id] varchar(50)
)

-------------////////////CREATE TABLE [stg].[Feed_Info]  //////////////----------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Feed_Info]') IS NOT NULL
DROP TABLE [stg].[Feed_Info]

CREATE TABLE [stg].[Feed_Info] (
    [feed_publisher_name] varchar(50),
    [feed_publisher_url] varchar(50),
    [feed_lang] varchar(50),
    [feed_start_date] varchar(50),
    [feed_end_date] varchar(50)
)



-----------------///////// CREATE [stg].[Frequencies_Staging] ////////-------------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Frequencies_Staging]') IS NOT NULL
DROP TABLE [stg].[Frequencies_Staging]

CREATE TABLE [stg].[Frequencies_Staging] (
    [trip_id] varchar(50),
    [start_time] varchar(50),
    [end_time] varchar(50),
    [headway_secs] varchar(50)
)


-------------////////////CREATE TABLE [stg].[Location_Staging]  //////////////----------------
USE STM_SRC
GO

IF OBJECT_ID('[stg].[Location_Staging]', 'U') IS NOT NULL 
  DROP TABLE [stg].[Location_Staging]; 

CREATE TABLE [stg].[Location_staging](
	[district] [varchar](500) NULL,
	[postal_code] [nvarchar](500) NULL,
	[stop_lat] [varchar](500) NULL,
	[stop_lon] [nvarchar](500) NULL,
	[row] [nvarchar](500) NULL,
	[District_OK] [nvarchar](500) NULL
) 


-------------///////////// CREATE [stg].[Routes_Staging] ////////////-------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Routes_Staging]') IS NOT NULL
DROP TABLE [stg].[Routes_Staging]


CREATE TABLE [stg].[Routes_Staging] (
    [route_id] varchar(50),
    [agency_id] varchar(50),
    [route_short_name] varchar(50),
    [route_long_name] varchar(50),
    [route_type] varchar(50),
    [route_url] varchar(50),
    [route_color] varchar(50),
    [route_text_color] varchar(50)
)

-------------///////////// CREATE [stg].[Shapes_Staging] ////////////-------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Shapes_Staging]') IS NOT NULL
DROP TABLE [stg].[Shapes_Staging]


CREATE TABLE [stg].[Shapes_Staging] (
    [shape_id] varchar(50),
    [shape_pt_lat] varchar(50),
    [shape_pt_lon] varchar(50),
    [shape_pt_sequence] varchar(50)
)

--------/////// CREATE TABLE [stg].[Source_Stops_Staging]  ///////////---------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Source_Stops_Staging]') IS NOT NULL
DROP TABLE [stg].[Source_Stops_Staging]

CREATE TABLE [stg].[Source_Stops_Staging] (
    [stop_id] varchar(500),
    [stop_code] varchar(500),
    [stop_name] varchar(500),
    [stop_lat] varchar(500),
    [stop_lon] varchar(500),
    [stop_url] varchar(500),
    [location_type] varchar(500),
    [parent_station] varchar(500),
    [wheelchair_boarding] varchar(500)
)


-------------///////////// CREATE [stg].[Stop_Times_Staging] ////////////-------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Stop_Times_Staging]') IS NOT NULL
DROP TABLE [stg].[Stop_Times_Staging]

CREATE TABLE [stg].[Stop_Times_Staging] (
    [trip_id] varchar(50),
    [arrival_time] varchar(50),
    [departure_time] varchar(50),
    [stop_id] varchar(50),
    [stop_sequence] varchar(50)
)



------------////////// CREATE TABLE [stg].[Trips_Staging] //////////////----------------
USE STM_SRC
GO

IF OBJECT_ID ('[stg].[Trips_Staging]') IS NOT NULL
DROP TABLE [stg].[Trips_Staging]

CREATE TABLE [stg].[Trips_Staging] (
    [route_id] varchar(500),
    [service_id] varchar(500),
    [trip_id] varchar(500),
    [trip_headsign] varchar(500),
    [direction_id] varchar(500),
    [shape_id] varchar(500),
    [wheelchair_accessible] varchar(500),
    [note_fr] varchar(500),
    [note_en] varchar(500)
)




----------------------////////////////////////////////////////////---------------------------------------
----------------------////////////////   DBO TABLES     //////////---------------------------------------
----------------------////////////////////////////////////////////---------------------------------------


-----------///////////Create Agency DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[STM_SRC].[dbo].[Agency]', 'U') IS NOT NULL 
  DROP TABLE [STM_SRC].[dbo].[Agency];

CREATE TABLE [STM_SRC].[dbo].[Agency] (
    [agency_id] varchar(50),
    [agency_name] varchar(50),
    [agency_url] varchar(50),
    [agency_timezone] varchar(50),
    [agency_lang] varchar(50),
    [agency_phone] varchar(50),
    [agency_fare_url] varchar(50)
)


-----------///////////Create Calendar_dates DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Calendar_dates]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Calendar_dates];

 CREATE TABLE [dbo].[Calendar_dates] (
    [service_id] nvarchar(50),
    [date] nvarchar(50),
    [exception_type] nvarchar(50)
)

-----------///////////Create Fare_attributes DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Fare_attributes]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Fare_attributes]; 


CREATE TABLE [dbo].[Fare_attributes] (
    [fare_id] nvarchar(50),
    [price] nvarchar(50),
    [payment_method] nvarchar(50),
    [transfers] nvarchar(50),
    [currency_type] nvarchar(50),
    [transfer_duration] nvarchar(50)
)


----------------///////////Create Fare_Rules DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Fare_rules]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Fare_rules];

  CREATE TABLE [dbo].[Fare_rules] (
    [fare_id] nvarchar(50),
    [route_id] nvarchar(50),
    [origin_id] nvarchar(50),
    [destination_id] nvarchar(50),
    [contains_id] nvarchar(50)
)



--------------------------///////////Create Feed DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Feed_info]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Feed_info];


  CREATE TABLE [dbo].[Feed_info](
	[feed_lang] [nvarchar](50) NULL,
	[feed_publisher_url] [nvarchar](50) NULL,
	[feed_publisher_name] [nvarchar](50) NULL,
	[feed_start_date] [nvarchar](50) NULL,
	[feed_end_date] [nvarchar](50) NULL
)


--------------------------///////////Create Frequencies DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Frequencies]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Frequencies];

  CREATE TABLE [dbo].[Frequencies] (
    [trip_id] nvarchar(50),
    [start_time] nvarchar(50),
    [end_time] nvarchar(50),
    [headway_secs] nvarchar(50)
)


-------------////////////CREATE TABLE [dbo].[Location]  //////////////----------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Location]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Location]; 

CREATE TABLE [dbo].[Location](
	[stop_lat] [varchar](500) NULL,
	[stop_lon] [nvarchar](500) NULL,
	[row] [nvarchar](500) NULL,
	[District] [nvarchar](500) NULL,
	[PostalCode] [nvarchar](500) NULL
) 

-----------------///////////Create Routes DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Routes]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Routes]; 


  CREATE TABLE [dbo].[Routes](
	[route_id] [nvarchar](500) NULL,
	[agency_id] [nvarchar](50) NULL,
	[route_short_name] [nvarchar](50) NULL,
	[route_long_name] [nvarchar](50) NULL,
	[route_type] [nvarchar](50) NULL,
	[route_url] [nvarchar](50) NULL,
	[route_color] [nvarchar](50) NULL,
	[route_text_color] [nvarchar](50) NULL
	)



----------------------------///////////Create Shapes DBO /////////////------------

USE STM_SRC
GO


IF OBJECT_ID('[dbo].[Shapes]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Shapes]; 

CREATE TABLE [dbo].[Shapes](
	[shape_id] [nvarchar](50) NULL,
	[shape_pt_lat] [nvarchar](50) NULL,
	[shape_pt_lon] [nvarchar](50) NULL,
	[shape_pt_sequence] [nvarchar](50) NULL
) 

---------------------------///////////Create STOP times DBO /////////////------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Stop_times]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Stop_times];


CREATE TABLE [dbo].[Stop_times] (
    [trip_id] nvarchar(50),
    [arrival_time] nvarchar(50),
    [departure_time] nvarchar(50),
    [stop_id] nvarchar(50),
    [stop_sequence] nvarchar(50),
    [Hour_ArrivalTime] nvarchar(50),
    [Minutes_ArrivalTime] nvarchar(50),
    [Seconds_ArrivalTime] nvarchar(2),
    [Hour_DepartureTime] nvarchar(50),
    [Minutes_DepartureTime] nvarchar(50),
    [Seconds_DepartureTime] nvarchar(2)
)


-------------------///////////Create STOPS DBO /////////////--------------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Stops]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Stops]; 


  CREATE TABLE [dbo].[Stops] (
    [stop_id] nvarchar(500),
    [stop_code] nvarchar(500),
    [stop_name] nvarchar(500),
    [stop_lat] nvarchar(500),
    [stop_lon] nvarchar(500),
    [stop_url] nvarchar(500),
    [location_type] nvarchar(500),
    [parent_station] nvarchar(500),
    [wheelchair_boarding] nvarchar(500)
)


--------------------///////////Create Trips DBO /////////////--------------------------
USE STM_SRC
GO

IF OBJECT_ID('[dbo].[Trips]', 'U') IS NOT NULL 
  DROP TABLE [dbo].[Trips]; 

  CREATE TABLE [dbo].[Trips](
	[route_id] [nvarchar](500) NULL,
	[service_id] [nvarchar](500) NULL,
	[trip_id] [nvarchar](500) NOT NULL,
	[trip_headsign] [nvarchar](500) NULL,
	[direction_id] [nvarchar](500) NULL,
	[shape_id] [nvarchar](500) NULL,
	[wheelchair_accessible] [nvarchar](500) NULL,
	[note_fr] [nvarchar](500) NULL,
	[note_en] [nvarchar](500) NULL
)

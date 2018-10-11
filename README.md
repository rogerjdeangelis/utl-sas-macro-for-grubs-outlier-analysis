# utl-sas-macro-for-grubs-outlier-analysis
SAS macro for grubs outlier analysis.
    SAS macro for grubs outlier analysis                                                                                                
                                                                                                                                        
    github                                                                                                                              
    https://github.com/rogerjdeangelis/utl-sas-macro-for-grubs-outlier-analysis                                                         
                                                                                                                                        
    related post                                                                                                                        
    https://github.com/rogerjdeangelis/utl-grubs-test-for-outliers-using-r-package-outliers                                             
                                                                                                                                        
    macro on end and in repository macros                                                                                               
    https://tinyurl.com/y9nfugth                                                                                                        
    https://github.com/rogerjdeangelis/utl-macros-used-in-many-of-rogerjdeangelis-repositories                                          
                                                                                                                                        
    INPUT                                                                                                                               
    =====                                                                                                                               
                                                                                                                                        
    WORK.SHOES total obs=395                                                                                                            
                                                                                                                                        
      REGION    PRODUCT           SUBSIDIARY       SALES                                                                                
                                                                                                                                        
      Africa    Boot              Addis Ababa      $360,209                                                                             
      Africa    Men's Casual      Addis Ababa      $353,361                                                                             
      Africa    Men's Dress       Addis Ababa      $757,798                                                                             
      Africa    Sandal            Addis Ababa      $700,513                                                                             
      Africa    Slipper           Addis Ababa      $756,347                                                                             
      Africa    Sport Shoe        Addis Ababa      $576,112                                                                             
      Africa    Women's Casual    Addis Ababa      $476,638                                                                             
      Africa    Women's Dress     Addis Ababa      $375,817                                                                             
      Africa    Boot              Algiers          $340,201                                                                             
      Africa    Men's Casual      Algiers          $419,336                                                                             
      Africa    Men's Dress       Algiers          $387,680                                                                             
                                                                                                                                        
                                                                                                                                        
    EXAMPLE OUTPUT                                                                                                                      
    --------------                                                                                                                      
                                                                                                                                        
    POTENTIAL OUTLIERS                                                                                                                  
                                                                                                                                        
    WORK.UTL_GRUBBS01 total obs=395  (potential outliers)                                                                               
                                                                                                                                        
                                                                                                                                        
    Obs    REGION                       PRODUCT           SUBSIDIARY        SALES                                                       
                                                                                                                                        
     17    Africa                       Men's Casual      Cairo          $360,209                                                       
    101    Canada                       Men's Casual      Vancouver      $353,361                                                       
    102    Canada                       Men's Dress       Vancouver      $757,798                                                       
    104    Canada                       Slipper           Vancouver      $700,513                                                       
    107    Canada                       Women's Dress     Vancouver      $756,347                                                       
    109    Central America/Caribbean    Men's Casual      Kingston       $576,112                                                       
    112    Central America/Caribbean    Slipper           Kingston       $476,638                                                       
    115    Central America/Caribbean    Women's Dress     Kingston       $375,817                                                       
    172    Middle East                  Men's Casual      Al-Khobar      $340,201                                                       
    180    Middle East                  Men's Casual      Dubai          $419,336                                                       
    183    Middle East                  Slipper           Dubai          $387,680                                                       
    186    Middle East                  Women's Dress     Dubai          $435,891                                                       
    188    Middle East                  Men's Casual      Tel Aviv     $1,298,717   **                                                  
    194    Middle East                  Women's Dress     Tel Aviv       $434,496                                                       
    211    Pacific                      Men's Casual      Jakarta        $373,908                                                       
    295    United States                Men's Casual      Chicago        $408,978                                                       
    319    United States                Men's Casual      New York       $456,985                                                       
    340    Western Europe               Women's Casual    Copenhagen     $502,636                                                       
                                                                                                                                        
                                                                                                                                        
    STATS ON OUTLIERS                                                                                                                   
                                                                                                                                        
    WORK.Utl_Grubbs01 total obs=395                                                                                                     
                                                                                                                                        
                                                         MIN_       MAX_       MEAN_        STD_                                        
    Obs    GRBTEST    GRBALPHA    GRBOBS    GRBDROP    GRBVALS    GRBVALS     GRBVALS     GRBVALS     GRBCALC    GRBCRIT    GRBPSTAT    
                                                                                                                                        
      1      Max        0.05        395       188        325      1298717    85700.17    129107.23    9.39542    3.63037     0.0000     
      2      Max        0.05        394       102        325       757798    82621.44    113831.21    5.93138    3.63021     0.0000     
      3      Max        0.05        393       107        325       756347    80903.44    108741.54    6.21146    3.63006     0.0000     
      4      Max        0.05        392       104        325       700513    79180.37    103369.12    6.01081    3.62990     0.0000     
      5      Max        0.05        391       109        325       576112    77591.28     98590.87    5.05646    3.62974     0.0001     
      6      Max        0.05        390       340        325       502636    76313.02     95418.19    4.46794    3.62958     0.0012     
      7      Max        0.05        389       112        325       476638    75217.08     93050.86    4.31399    3.62943     0.0025     
      8      Max        0.05        388       319        325       456985    74182.49     90903.15    4.21110    3.62927     0.0040     
      9      Max        0.05        387       186        325       435891    73193.33     88905.45    4.07959    3.62910     0.0073     
     10      Max        0.05        386       194        325       434496    72253.70     87075.46    4.16010    3.62894     0.0050     
     11      Max        0.05        385       180        325       419336    71312.81     85201.39    4.08471    3.62878     0.0071     
     12      Max        0.05        384       295        325       408978    70406.50     83433.60    4.05798    3.62862     0.0079     
     13      Max        0.05        383       183        325       387680    69522.50     81722.24    3.89316    3.62845     0.0163     
     14      Max        0.05        382       115        325       375817    68689.63     80185.27    3.83022    3.62829     0.0212     
     15      Max        0.05        381       211        325       373908    67883.52     78725.58    3.88723    3.62812     0.0166     
     16      Max        0.05        380        17        325       360209    67078.19     77241.96    3.79497    3.62796     0.0244     
     17      Max        0.05        379       101        325       353361    66304.76     75856.36    3.78421    3.62779     0.0255     
     18      Max        0.05        378       172        325       340201    65545.35     74500.34    3.68664    3.62762     0.0379     
                                                                                                                                        
                                                                                                                                        
    PROCESS                                                                                                                             
    =======                                                                                                                             
                                                                                                                                        
      %utl_Grubbs(sashelp.shoes,sales,alpha=.05);                                                                                       
                                                                                                                                        
    *                _              _       _                                                                                           
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _                                                                                    
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |                                                                                   
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |                                                                                   
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|                                                                                   
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
    data shoes;                                                                                                                         
      set sashelp.shoes(keep=region product subsidiary stores sales);                                                                   
    run;quit;                                                                                                                           
                                                                                                                                        
    *                                                                                                                                   
     _ __ ___   __ _  ___ _ __ ___                                                                                                      
    | '_ ` _ \ / _` |/ __| '__/ _ \                                                                                                     
    | | | | | | (_| | (__| | | (_) |                                                                                                    
    |_| |_| |_|\__,_|\___|_|  \___/                                                                                                     
                                                                                                                                        
    ;                                                                                                                                   
                                                                                                                                        
                                                                                                                                        
    %macro utl_Grubbs(dsn,var,alpha=.1)                                                                                                 
        /des ="Alternating removal of Max and Min Outliers using Grubbs test";                                                          
                                                                                                                                        
    /* output dataset is the input dataset with outlier flag */                                                                         
                                                                                                                                        
    /* for testing without macro                                                                                                        
       data shoes;set sashelp.shoes(keep=sales);run;                                                                                    
       %let dsn=work.shoes;                                                                                                             
       %let var=sales;                                                                                                                  
       %let alpha=.1;                                                                                                                   
    */                                                                                                                                  
                                                                                                                                        
       %local utl_grbnobs;                                                                                                              
                                                                                                                                        
       %put %sysfunc(ifc(%sysevalf(%superq(dsn)=,boolean),**** Please Input dataset                   ****,));                          
       %put %sysfunc(ifc(%sysevalf(%superq(var)=,boolean),**** Please Input Variable                  ****,));                          
                                                                                                                                        
       proc means data=&dsn;                                                                                                            
       var &var;                                                                                                                        
       output out=__out__ mean=mean std=std max=max min=min n=n;                                                                        
       run;                                                                                                                             
       /*------------------------------------------------------------*\                                                                 
       |  Add a unique key so that Outliers can be removed            |                                                                 
       \*------------------------------------------------------------*/                                                                 
        Data  Utl_Grubbs00 / View = Utl_Grubbs00;                                                                                       
         Set  &dsn(Keep=&var);                                                                                                          
              Utl_GrbKey=_n_;                                                                                                           
        Run;                                                                                                                            
       /*------------------------------------------------------------*\                                                                 
       |  Sort so that we can trim both ends easily                   |                                                                 
       \*------------------------------------------------------------*/                                                                 
        Proc Sort Data=Utl_Grubbs00                                                                                                     
                  Out =Utl_Grubbs01                                                                                                     
                  Noequals                                                                                                              
                  Force;                                                                                                                
        By  &var;                                                                                                                       
       run;                                                                                                                             
       /*------------------------------------------------------------*\                                                                 
       |  Need to get number of obds and Type and Length for Key      |                                                                 
       \*------------------------------------------------------------*/                                                                 
       Proc Sql Noprint;                                                                                                                
          Select Put(Nobs,12.)  into :Utl_GrbNobs                                                                                       
          From   SASHELP.VTable                                                                                                         
          Where  Upcase("WORK")           = Upcase(LibName)   AND                                                                       
                 Upcase("Utl_Grubbs01")   = Upcase(MemName)   AND                                                                       
                 Upcase("Data")           = Upcase(MemType);                                                                            
       quit;                                                                                                                            
       run;                                                                                                                             
       /*------------------------------------------------------------*\                                                                 
       |  Compute the Grubbs Statistics                               |                                                                 
       \*------------------------------------------------------------*/                                                                 
       Data                                                                                                                             
             Utl_Grubbs02                                                                                                               
                (                                                                                                                       
                 Keep=                                                                                                                  
                       GrbTest                                                                                                          
                       GrbAlpha                                                                                                         
                       GrbObs                                                                                                           
                       GrbDrop                                                                                                          
                       Min_GrbVals                                                                                                      
                       Max_GrbVals                                                                                                      
                       Mean_GrbVals                                                                                                     
                       Std_GrbVals                                                                                                      
                       GrbCalc                                                                                                          
                       GrbCrit                                                                                                          
                       GrbPStat                                                                                                         
                );                                                                                                                      
                                                                                                                                        
         Retain GrbNobs &Utl_GrbNobs GrbAlpha &Alpha;                                                                                   
       /*------------------------------------------------------------*\                                                                 
       |  Allocate arrays to hold all data                            |                                                                 
       \*------------------------------------------------------------*/                                                                 
         Array  GrbVals {&Utl_GrbNobs}  _Temporary_;                                                                                    
         Array  GrbKeys {&Utl_GrbNobs}  _Temporary_;                                                                                    
       /*------------------------------------------------------------*\                                                                 
       |  Load all Data into Temp Arrays - Temp Arrays can have       |                                                                 
       |  millions of elements?                                       |                                                                 
       \*------------------------------------------------------------*/                                                                 
         GrbN=0;                                                                                                                        
         Do Until ( Done );                                                                                                             
            Set Utl_Grubbs01 End=Done;                                                                                                  
            GrbN+1;                                                                                                                     
            GrbKeys{GrbN} = Utl_GrbKey;                                                                                                 
            GrbVals{GrbN} = &var;                                                                                                       
         End;                                                                                                                           
         /*------------------------------------------------------------*\                                                               
         | Cannot use more elegant Mean(of Array), Std(Of Array)        |                                                               
         | SAS does not support these funtions on Temporary Arrays      |                                                               
         \*------------------------------------------------------------*/                                                               
         GrbObs=GrbNobs;                                                                                                                
         GrbLo=1;                                                                                                                       
         GrbHi=GrbObs;                                                                                                                  
         Do  Until ( GrbFlag = 1 )  ;                                                                                                   
             GrbFlag=0;                                                                                                                 
          Link BasicStats;                                                                                                              
                       *  Pass=GrbLo,GrbHi,Array GrbVals                                                                                
                          Return=Mean,Max,Min,Std;                                                                                      
          * Put      "Max Basic Stats ==>  "     /                                                                                      
                      GrbObs        =            /                                                                                      
                      GrbHi         =            /                                                                                      
                      GrbLo         =            /                                                                                      
                      Min_GrbVals   =            /                                                                                      
                      Max_GrbVals   =            /                                                                                      
                      Mean_GrbVals  =            /                                                                                      
                      Std_GrbVals   = ;                                                                                                 
          /*------------------------------------------------------------*\                                                              
          | Maximum Outlier Case                                         |                                                              
          \*------------------------------------------------------------*/                                                              
          GrbTest='Max';                                                                                                                
          GrbCalc    =( Max_GrbVals - Mean_GrbVals ) / Std_GrbVals ;                                                                    
          GrbTStat   =TInv(1-&Alpha/GrbNobs,GrbNobs-2);                                                                                 
          Link GrbCompute;                                                                                                              
                           * Pass=GrbCalc,GrbTStat,GrbObs                                                                               
                             Return=GrbCrit GrbStat GrbPStat;                                                                           
          * put       // "Max Grubbs Stats ==>  "   /                                                                                   
                          GrbCrit=                  /                                                                                   
                          GrbStat=                  /                                                                                   
                          GrbDenom=                 /                                                                                   
                          GrbPStat=;                                                                                                    
          If GrbPStat < GrbAlpha Then                                                                                                   
              GrbHi = GrbHi - 1;                                                                                                        
          Else GrbFlag = GrbFlag + .5;                                                                                                  
          * put          //  GrbFlag= //;                                                                                               
          /*------------------------------------------------------------*\                                                              
          | Recompute Basic Stats without Outlier                        |                                                              
          \*------------------------------------------------------------*/                                                              
          Link BasicStats; * (GrbLo,GrbHi);                                                                                             
          *       Put // "Min Basic Stats ==>  " /                                                                                      
                      GrbObs        =            /                                                                                      
                      GrbObs        =            /                                                                                      
                      GrbHi         =            /                                                                                      
                      Min_GrbVals   =            /                                                                                      
                      Max_GrbVals   =            /                                                                                      
                      Mean_GrbVals  =            /                                                                                      
                      Std_GrbVals   = ;                                                                                                 
          /*------------------------------------------------------------*\                                                              
          | Minimum Outlier Case                                         |                                                              
          \*------------------------------------------------------------*/                                                              
          GrbTest='Min';                                                                                                                
          GrbCalc    =( Mean_GrbVals - Min_GrbVals) / Std_GrbVals ;                                                                     
          GrbTStat   =TInv(&alpha/GrbNobs,GrbNobs-2);                                                                                   
          Link GrbCompute;                                                                                                              
          * Put       // "Min Grubbs Stats ==>  "  /                                                                                    
                            GrbCrit=               /                                                                                    
                            GrbStat=               /                                                                                    
                            GrbDenom=              /                                                                                    
                            GrbPStat=;                                                                                                  
          If GrbPStat < GrbAlpha Then                                                                                                   
              GrbLo = GrbLo + 1;                                                                                                        
          Else GrbFlag = GrbFlag + .5;                                                                                                  
          * put          //  GrbFlag= // I=;                                                                                            
      End;                                                                                                                              
      Stop;                                                                                                                             
      ENDIT: Put "Cannot Have missing values for Obsevations";                                                                          
      Stop;                                                                                                                             
      /*------------------------------------------------------------*\                                                                  
      |  Compute Grubbs Statistics                                   |                                                                  
      \*------------------------------------------------------------*/                                                                  
      GrbCompute:                                                                                                                       
          GrbCrit    =((GrbObs-1)/sqrt(GrbObs))*sqrt(GrbTStat**2/(GrbObs-2+GrbTStat**2));                                               
          GrbDenom   =(GrbCalc**2*GrbObs-(GrbObs-1)**2);                                                                                
            Select;                                                                                                                     
              When ( GrbDenom =.   ) GoTo ENDIT;                                                                                        
              When ( GrbDenom <  0 ) GrbStat=sqrt(-(GrbCalc**2*GrbObs*(GrbObs-2)/GrbDenom));                                            
              When ( GrbDenom  = 0 ) GrbStat=sqrt(GrbCalc**2*GrbObs*(GrbObs-2)/GrbDenom);                                               
            OtherWise ;                                                                                                                 
            End;                                                                                                                        
            If  GrbStat =. then GoTo ENDIT;                                                                                             
            GrbPStat=Min(GrbObs*(1-ProbT(GrbStat,GrbObs-2)),1);                                                                         
            If GrbPStat < GrbAlpha Then Do;                                                                                             
               If GrbTest='Min' Then GrbDrop=GrbKeys{GrbLo};                                                                            
               Else GrbDrop=GrbKeys{GrbHi};                                                                                             
               Output;                                                                                                                  
            End;                                                                                                                        
      Return;                                                                                                                           
      /*------------------------------------------------------------*\                                                                  
      |  Compute MeanStandard Deviation                              |                                                                  
      \*------------------------------------------------------------*/                                                                  
      BasicStats:                                                                                                                       
          GrbObs=( GrbHi - GrbLo + 1 );                                                                                                 
          SumSq_GrbVals=0;                                                                                                              
          Sum_GrbVals=0;                                                                                                                
          Do I = GrbLo To GrbHi;                                                                                                        
             SumSq_GrbVals +  GrbVals{I}**2;                                                                                            
             Sum_GrbVals   +  GrbVals{I};                                                                                               
          End;                                                                                                                          
          Std_GrbVals=Sqrt(                                                                                                             
                           (  GrbHi*SumSq_GrbVals - Sum_GrbVals**2 ) /                                                                  
                           (  GrbObs* ( GrbObs- 1 )                )                                                                    
                          );                                                                                                            
          Max_GrbVals=GrbVals{GrbHi};                                                                                                   
          Min_GrbVals=GrbVals{GrbLo};                                                                                                   
          Mean_GrbVals= Sum_GrbVals / GrbObs;                                                                                           
      Return;                                                                                                                           
      Run;                                                                                                                              
                                                                                                                                        
                                                                                                                                        
      Proc print Data=utl_Grubbs02  Width=Min;                                                                                          
        Format GrbPStat 6.4;                                                                                                            
        Var                                                                                                                             
          GrbTest                                                                                                                       
          GrbAlpha                                                                                                                      
          GrbObs                                                                                                                        
          GrbDrop                                                                                                                       
          Min_GrbVals                                                                                                                   
          Max_GrbVals                                                                                                                   
          Mean_GrbVals                                                                                                                  
          Std_GrbVals                                                                                                                   
          GrbCalc                                                                                                                       
          GrbCrit                                                                                                                       
          GrbPStat;                                                                                                                     
       Run;                                                                                                                             
      /*------------------------------------------------------------*\                                                                  
      | Put in same order as original input                          |                                                                  
      \*------------------------------------------------------------*/                                                                  
      Proc Sort                                                                                                                         
           Data = Utl_Grubbs01                                                                                                          
           Out  = Utl_Grubbs01(Index= ( Utl_GrbKey / Unique ));                                                                         
      By   Utl_GrbKey;                                                                                                                  
      Run;                                                                                                                              
      /*------------------------------------------------------------*\                                                                  
      | Tag the Outliers ( Use SQL just to keep skills up )          |                                                                  
      \*------------------------------------------------------------*/                                                                  
      Proc Sql;                                                                                                                         
          Alter  Table  Utl_Grubbs01                                                                                                    
          Modify _Outlier_ num;                                                                                                         
          Update Utl_Grubbs01                                                                                                           
          Set    _Outlier_ =                                                                                                            
            (                                                                                                                           
             Select  1                                                                                                                  
             From    utl_Grubbs02                                                                                                       
             Where   GrbDrop = Utl_GrbKey                                                                                               
             );                                                                                                                         
       Quit;                                                                                                                            
       Run;                                                                                                                             
      /*------------------------------------------------------------*\                                                                  
      | Concatenate _Outlier_ onto original raw data                 |                                                                  
      \*------------------------------------------------------------*/                                                                  
      options mergenoby=nowarn;                                                                                                         
      Data &dsn;                                                                                                                        
         Merge &dsn                                                                                                                     
               Utl_Grubbs01(Keep=_Outlier_);                                                                                            
        /*------------------------------------------------------------*\                                                                
        |  No By Statement ( Data in Exactly the same order )          |                                                                
        |  By Variable not on Raw Input Table                          |                                                                
        \*------------------------------------------------------------*/                                                                
          If _Outlier_ = . then _Outlier_ = 0;                                                                                          
      Run;                                                                                                                              
      options mergenoby=warn;                                                                                                           
      Proc Print                                                                                                                        
                 Data=&dsn(where=(_Outlier_=1));                                                                                        
      run;                                                                                                                              
    %mend Utl_Grubbs;                                                                                                                   
                                                                                                                                        
    %utl_Grubbs(sashelp.shoes,sales,alpha=.05);                                                                                         
                                                                                                                                        
                                                                                                                                        
                                                                                                                                        

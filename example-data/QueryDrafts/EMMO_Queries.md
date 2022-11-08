1. Welche Materialien sind in den Daten vorhanden?
    ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?material_instance rdf:type emmo:EMMO_4207e895_8b83_4318_996a_72cfb32acd94;         #emmo:Material
    }
    ```
2. Welche Eigenschaften haben die Materialien (oder ein bestimmtes)?
    - z.B. welche Masse haben die vorhandenen Samples?
    - z.B. welche Größe haben die beteiligten gekochten Eier?

    ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?material_instance rdf:type emmo:EMMO_4207e895_8b83_4318_996a_72cfb32acd94;         #emmo:Material
                emmo:EMMO_e1097637_70d2_4895_973f_2396f04fa204 ?material_property_instance.     #emmo:hasProperty
    }
    ```

3. Welche Prozesse sind in den Daten vorhanden?

    ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce.         #emmo:Process
               
    }
    ```
4. Welche Prozessschritte (Teilprozesse) gibt es?

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               emmo:EMMO_f22abf74_4538_4f50_ab85_09908cdda707 ?process_stage #emmo:hasStage
    }
    ```

5. Welche Parameter haben die Prozesse (oder ein bestimmter (Teil-)Prozess)

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               emmo:EMMO_e1097637_70d2_4895_973f_2396f04fa204 ?process_parameter #emmo:hasProperty
    }
    ```
    Variante benutzen chameo domain ontology
    ```
    PREFIX emmo: <http://emmo.info/emmo#>
    PREFIX chameo: <http://emmo.info/emmo/domain/chameo/chameo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               chameo:hasMeasurementParameter ?process_parameter #emmo:hasProperty
    }
    ```
6. Welche Eigenschaften (Settings/Einstellungen/Input) haben die Prozesse?

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               emmo:EMMO_36e69413_8c59_4799_946c_10b05d266e22 ?specimen_instance #emmo:hasInput

        OPTIONAL { emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce emmo:EMMO_36e69413_8c59_4799_946c_10b05d266e22 ?specimen_instance } #emmo:hasInput       

        OPTIONAL { emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce emmo:EMMO_ae2d1a96_bfa1_409a_a7d2_03d69e8a125a ?machine_instance . #emmo:hasParticipant
        ?machine_instance rdf:type emmo:EMMO_f2d5d3ad_2e00_417f_8849_686f3988d929 . #MeasuringInstrument
        }          
    }
    ```

7. Welche Tests sind vorhanden?

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?measurement_instance rdf:type emmo:EMMO_463bcfda_867b_41d9_a967_211d4d437cfb.         #emmo:Measurement
    }
    ```


8. Welche Prozesse sind an den Tests (oder einem bestimmten) beteiligt?

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?measurement_instance rdf:type emmo:EMMO_463bcfda_867b_41d9_a967_211d4d437cfb;         #emmo:Measurement
            emmo:EMMO_f22abf74_4538_4f50_ab85_09908cdda707 ?process_stage . #emmo:hasStage
    }
    ```

9. Welche Prozesse sind an den Tests (oder einem bestimmten) beteiligt?

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?measurement_instance rdf:type emmo:EMMO_463bcfda_867b_41d9_a967_211d4d437cfb;         #emmo:Measurement
            emmo:EMMO_f22abf74_4538_4f50_ab85_09908cdda707 ?process_stage . #emmo:hasStage
    }
    ```

10. Welche Datasets sind vorhanden?
     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?measurement_instance rdf:type emmo:EMMO_194e367c_9783_4bf5_96d0_9ad597d48d9a .         #emmo:DataSet

    }
    ```

11. Welche Geräte sind an einem Prozess beteiligt?
     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
        ?process_instance rdf:type emmo:EMMO_43e9a05d_98af_41b4_92f6_00f79a09bfce;         #emmo:Process
               emmo:EMMO_ae2d1a96_bfa1_409a_a7d2_03d69e8a125a ?machine_instance #emmo:hasParticipant      
        ?machine_instance rdf:type emmo:EMMO_f2d5d3ad_2e00_417f_8849_686f3988d929 . #MeasuringInstrument

    }
    ```

12. Wie haben sich Eigenschaften verändert über Prozesse und deren Schritte hinweg? (vorher/nachher Wert)

Kommentar: Ich habe diese Frage aus Specimen Sicht beantwortet.

     ```
    PREFIX emmo: <http://emmo.info/emmo#>

    SELECT * WHERE{
   

    }
    ```
(12) Wie haben sich Eigenschaften verändert über Prozesse und deren Schritte hinweg? (vorher/nachher Wert)

-- Weitere evtl. noch zu klärenden Fragen:

(13) Wie können Eigenschaften und Messergebnisse unterschieden werden?

(14) Wie können Material und Mikrostruktur unterschieden werden?
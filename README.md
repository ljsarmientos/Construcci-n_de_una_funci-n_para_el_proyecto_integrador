DELIMITER //

CREATE FUNCTION calcular_calificacion_promedio(docente_id INT)
RETURNS FLOAT
BEGIN
    DECLARE promedio FLOAT;

    -- Calcula el promedio de las calificaciones para el docente especificado
    SELECT AVG(calificacion) INTO promedio
    FROM respuestas_encuesta
    WHERE id_docente = docente_id;

    RETURN promedio;
END //

DELIMITER ;



    --La función calcular_calificacion_promedio toma el identificador del docente (docente_id) como argumento.
    Usa la función AVG para calcular el promedio de las calificaciones (calificacion) de las respuestas de la tabla respuestas_encuesta.
    Retorna el promedio calculado.

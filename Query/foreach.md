<insert id="insertDb" parameterType="java.util.HashMap">
  <foreach collection="user_list" item="item" separator=";">
      <if test="item.id != null">
        insert into tb_user
        (
          id,
          name
        ) values (
          #{item.id},
          #{item.name}
        )
      </if>
  </foreach>
</insert>
<!-- user_list 가 null 이면 실행 안됨 : 당연. -->
